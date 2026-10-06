---
title: "evcc on an Old Laptop: Solar-Only Tesla Charging"
layout: post
date: 2026-10-06 21:00
image:
headerImage: false
tag:
- evcc
- ubuntu
- tesla
- fronius
- solar
star: false
category: blog
author:
description: Non-obvious fixes for evcc with a Tesla Wall Connector, Model 3 and Fronius GEN24
---

Setup: an ASUS Zenbook UX305FA (Intel 7265 Wi-Fi/Bluetooth) running Ubuntu Server 26.04 and evcc 0.316.2 (apt), with a Tesla Wall Connector Gen 3, a 2022 Model 3, and a Fronius Primo GEN24 with a Smart Meter. Follow the [evcc docs](https://docs.evcc.io) for everything else. Only the parts that needed a fix are covered here.

## 1. Fronius GEN24: Solar API Is Off by Default

The inverter replies `SolarAPI disabled by customer config`, and Modbus (port 502) is off too.

* Enable it in the inverter web UI under **Communication → Solar API**.
* In evcc, use the **Fronius Solar API V1** template for both the solar meter and the grid meter. The "Fronius Primo GEN24 Plus" template needs Modbus, and its validation fails with a YAML error in 0.316.2.

## 2. Tesla Vehicle

The TWC3 is read-only, so evcc controls charging by sending commands to the car. Those commands need a command proxy. MyTeslaMate's is paid, and without a valid token you get `401 Unauthorized: Invalid API key`. The free option is Bluetooth, covered in the next section.

## 3. Free Charging Commands over Bluetooth

[TeslaBleHttpProxy](https://github.com/wimaha/TeslaBleHttpProxy) sends commands to the car over Bluetooth, so the laptop has to be within a few metres of it.

```bash
sudo apt install bluez docker.io docker-compose-v2 docker-buildx
sudo systemctl enable --now bluetooth docker
```

### 3.1 Intel 7265 scan fix

The stock image always failed with `Vehicle is not in range: ble: failed to scan for <VIN>: context deadline exceeded`, even with the car 1 m away. Downgrading to 2.1.3 didn't help.

The cause is that Tesla's [vehicle-command](https://github.com/teslamotors/vehicle-command) library sets `ScanningFilterPolicy: 2`, and the Intel 7265 doesn't support extended scanner filter policies:

```bash
sudo hcitool -i hci0 cmd 0x08 0x0003   # LE feature byte 0x01 -> bit 7 (0x80) missing
```

The fix is to rebuild the proxy with policy `0`:

```bash
git clone --depth 1 -b 2.3.0 https://github.com/wimaha/TeslaBleHttpProxy.git && cd TeslaBleHttpProxy
git clone --depth 1 -b v0.0.7 https://github.com/wimaha/vehicle-command.git vc   # fork pinned in go.mod
sed -i 's/ScanningFilterPolicy: 2,/ScanningFilterPolicy: 0,/' vc/pkg/connector/ble/device_linux.go
sed -i 's#^replace github.com/teslamotors/vehicle-command => .*#replace github.com/teslamotors/vehicle-command => ./vc#' go.mod
sed -i 's#^WORKDIR .*teslaBleHttpProxy/#&\nENV GOFLAGS=-mod=mod#' Dockerfile
sudo docker buildx build --load -t tesla-ble-http-proxy:2.3.0-scanfix .
```

`docker-buildx` is required because the legacy builder fails on `--platform=${BUILDPLATFORM}`.

### 3.2 Run and pair

`docker-compose.yml` (run `mkdir -m 700 key` first, then `sudo docker compose up -d`):

```yaml
services:
  tesla-ble-http-proxy:
    image: tesla-ble-http-proxy:2.3.0-scanfix
    container_name: tesla-ble-http-proxy
    volumes:
      - ./key:/key
      - /var/run/dbus:/var/run/dbus
    restart: always
    privileged: true
    network_mode: host
    cap_add:
      - NET_ADMIN
      - SYS_ADMIN
```

1. In `http://<host>:8080/dashboard`, generate a **Charging Manager** key, wake the car, and send the key to the VIN. Tap the key card on the centre console straight away; the car shows no prompt.
2. Check it: `curl -s localhost:8080/api/1/vehicles/<VIN>/body_controller_state` should return `"result":true`. Before pairing, it returns `public key has not been paired`.
3. In evcc, go to vehicle → advanced and set **Command Proxy** to `http://localhost:8080`. Leave **Proxy Token** empty.

While the proxy runs, the host's `bluetoothctl` shows `No default controller available`. That's expected, because the proxy has exclusive control of `hci0`.

After section 3, everything else works as intended using the standard evcc setup.

## Thanks

Thanks to [Charge HQ](https://chargehq.net), which handled solar charging for my Tesla before the service closed. Their [alternatives page](https://chargehq.net/kb/alternatives-to-charge-hq) lists evcc among the replacement options.
