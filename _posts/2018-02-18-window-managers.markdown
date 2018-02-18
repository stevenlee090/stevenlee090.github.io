---
title: "Window Managers"
layout: post
date: 2018-02-18 21:52
image: /assets/images/markdown.jpg
headerImage: false
tag:
- chunkwm
- skhd
- spectacle
star: false
category: blog
author: stevenlee
description: Setup of window managers in macOS
---

![chunkwm Window Manager](/assets/images/chunkwm.jpg)
<figcaption class="caption">chunkwm for macOS</figcaption>

---

Just a few days before this website was created, I stumbled across [Richard Zhao's Blog](http://richard-zhao.com/blog/) which had a great tutorial explaining how to install kwm window manager for macOS. Up until that point, I had been using a relatively simple window manager called [Spectacle](https://www.spectacleapp.com). It provided basic features for snapping windows and manipulating their sizes, similar to Windows 10's default window managing shortcuts. However, it was not very customisable, nor flexible. Therefore, I decided to look into chunkwm (successor of kwm).

The [chunkwm official GitHub repository](https://github.com/koekeishiya/chunkwm) provided clear instructions and documentations regarding how to setup and customise the window manager. The [beginner's guide](http://hde-advent-2017.hatenadiary.jp/entry/2017/12/24/000000) listed in the repository was really well written, and by following this guide, I was able to complete the whole guided setup. While the configuration files listed in the guide was helpful, it is still worth checking out the official sample configuration files as there are more example operations listed in there.

See the following official configuration files:
* [chunkwmrc](https://github.com/koekeishiya/chunkwm/blob/master/examples/chunkwmrc)
* [skhdrc](https://github.com/koekeishiya/chunkwm/blob/master/src/plugins/tiling/examples/skhdrc)

I am currently using a slightly modified version of the official configuration files. Over time, everyone will develop their own set of habits and preferences for using chunkwm. For those who are interested, I would highly recommend chunkwm as it is highly customisable and versatile. Even though it takes a little while to learn, I believe most will benefit from the efficiency gain through the use of this window manager.

More information about the chunkwm can be found in the [official wiki](https://github.com/koekeishiya/chunkwm/wiki/Instructions:-chunkwm-with-(s)khd-on-macOS-High-Sierra).
