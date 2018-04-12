---
title: "NIARC Dev Blog 1"
layout: post
date: 2018-04-11 14:17
image: # /assets/images/iterm.png
headerImage: false
tag:
- national instrument
- autonomous robot
- robotics
- research
- development
star: false
category: blog
author: stevenlee
description: The first NIARC development blog post.
---

## What is NIARC?

In the NIARC Dev Blogs, I will be documenting and discussing the process of the robot car development. To start off, NIARC is the [National Instrument Autonomous Robotics Competition](http://australia.ni.com/ni-arc/) which runs on an annual basis. Universities around Australia and New Zealand sign up and compete with each other based on the predetermined tasks and obstacle course. The rules and challenges differ from year to year, and this encourages students to try out new designs and produce prototypes which are suitable for specific purposes. See the official [NIARC Facebook Page](https://www.facebook.com/niroboticscomp/) and [NIARC YouTube Channel](https://www.youtube.com/channel/UCYKerj0SwaT1BaTSi9Xxltw) for some footages from the past competitions.

## Ordering Parts

Since robot parts are extremely expensive in Australia, it was decided to order directly from Chinese vendors which offer more reasonable pricing on the robot parts. However, it turns out that not all the parts have the international shipping option enabled. Therefore, I started looking for alternative methods for purchasing the parts. Through a friend's recommendation, I came across [Cssbuy](www.cssbuy.com), a third party shipping forwarder which helps customers purchase products from in-land China, then have them shipped to the preferred overseas address.

The steps taken are outlined below:

1. Find out exactly what you need to buy from [Taobao](https://world.taobao.com).
2. Note down the Taobao hyperlink of the products, and its corresponding variant and quantity.
3. Create account / log in to Cssbuy.
4. Input the links and options noted down in step 2.
5. Charge up the account balance using PayPal.
6. Place the order and wait for items to arrive at the warehouse. (For a small fee you can request photos of the products to be taken, once they have arrived at the warehouse.)
7. Once all the ordered items have arrived at the warehouse, you can then ship the items using your preferred shipping method.

For me the items arrived in approximately one week after finalising the shipping details, which was a bit faster than I expected. It is also worth noting that the products were well packaged and a generous amount of bubble wraps were included to ensure that any potential damage to the goods was minimised.

## Initial Assembly

---

![iTerm2](/assets/images/devblog1/screws-wheels.jpg)
<figcaption class="caption">Screw threads, wheel mounting hub, mecanum wheel.</figcaption>

---

After finding the right tools (suitable screw drivers and soldering equipment), the assembly process becomes rather straightforward. However, I did have to stop at one point because the motor shaft had an interference fit with the wheel hub. This problem was addressed by using a metal file to increase the inner diameter of the wheel hub, just enough for the motor shaft to fit through.

---

![iTerm2](/assets/images/devblog1/motor-connector.jpg)
<figcaption class="caption">Motor connector</figcaption>

---

Overall, I quite enjoyed the process of putting together all the individual parts. Even though certain steps were repetitive, it was still quite amazing to see how we have the ability to produce such precise and user-friendly parts economically and have them shipped to the customers in such a short time frame.

---

![iTerm2](/assets/images/devblog1/robot-top.jpg)
<figcaption class="caption">Robot Car Assembly (Top View)</figcaption>

---

![iTerm2](/assets/images/devblog1/robot-side.jpg)
<figcaption class="caption">Robot Car Assembly (Side View)</figcaption>

---

![iTerm2](/assets/images/devblog1/wheel.jpg)
<figcaption class="caption">Mecanum Wheel</figcaption>

---

## Next Step

1. Complete pin assignment table
2. Basic programming of the robot car in LabView
3. Have the whole team complete the first milestone (**LabView Core 1 & 2** Training Exercises)
4. Name the robot
