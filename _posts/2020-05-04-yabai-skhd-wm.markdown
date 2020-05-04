---
title: "Tiling Window Manger (yabai)"
layout: post
date: 2020-05-04 20:00
image: # /assets/images/iterm.png
headerImage: false
tag:
- window manager
- chunkwm
- yabai
- skhd
star: false
category: blog
author: stevenlee
description: Notes taken while setting up yabai and skhd
---

![yabai Window Manager](/assets/images/yabai.jpg)
<figcaption class="caption">yabai for macOS</figcaption>

---

Few years ago, I posted about how I managed to [tiling window manager `chunkwm`]({% post_url 2018-02-18-window-managers %}), which is now deprecated and no longer maintained by [koekeishiya](https://github.com/koekeishiya). However, now we have a newer and greater window manager `yabai`, which I will be using from now onwards. Note that this is a macOS specific tiling window manager and I am installing this on macOS version 10.15.4.

## 1. Installing yabai
The [official wiki page](https://github.com/koekeishiya/yabai/wiki#yabai) is a is a great place to start, as it provides you with a great overview of what you are getting into. Plus, the GitHub Wiki sidebar has just about everything you would need to get this up and running.

To enable all yabai features, we are required to disable macOS's System Integrity Protection, the instructions is [here](https://github.com/koekeishiya/yabai/wiki/Disabling-System-Integrity-Protection). After that is done, you are ready to install the plugin as per instructions [here](https://github.com/koekeishiya/yabai/wiki/Installing-yabai-(latest-release)).

## 2. Installing skhd
Now we need a hotkey/shortcut manager, which will be `skhd` in this case. The install information is available on the [official repo](https://github.com/koekeishiya/skhd).

## 3. Getting Started with Example Config Files

* `yabai` and `skhd` [example config files](https://github.com/koekeishiya/yabai/tree/master/examples)
* `yabai` config file used by koekeishiya [here](https://github.com/koekeishiya/dotfiles/blob/master/yabai/yabairc)
* `skhd` config file used by koekeishiya [here](https://github.com/koekeishiya/dotfiles/blob/master/skhd/skhdrc)

While the example config files provide a brief overview of what can be achieved. I found it more helpful to directly look at koekeishiya's complete config. This is especially helpful if you are already used to the example bindings from `chunkwm`.

## 4. Customisation
Your friends are here:

* https://github.com/koekeishiya/yabai/blob/master/doc/yabai.asciidoc
* https://github.com/koekeishiya/yabai/wiki/Commands#display-commands

They are very well documented and easy to read. The approach I take is trial and error. Keep tweaking it until it fits your liking. Previously, I got quite used to the default bindings provided by `chunkwm` and `skhd`, so I ended up porting most of them over to `yabai`.

## 5. Status Bar

While various options presented below are available, I ended up going for the second one, which is almost identical to the Bitbar extension that I used to use with `chunkwm` except that this one is designed for `yabai`.

* [spacebar](https://github.com/somdoron/spacebar) which was originally shipped with yabai, but is now an independnet project on its own
* [yabai/skhd helper](https://getbitbar.com/contributors/jwon) a simple bitbar plugin that displays desktop ID and desktop mode of yabai.
* [yabai-spaces](https://github.com/SxC97/Yabai-Spaces) a bitbar plugin which provides support for yabai
* [nibar](https://github.com/kkga/nibar) a simple Übersicht widget status bar with yabai support

## 6. Other Issues

Below section(s) document some of the issues I ran into while setting `yabai` and `skhd`.

### 6.1 Window Resizing Ignored

If you are using `iTerm2` or some other terminal application, one difference that yabai differs from chunkwm is that it does not automatically resize the window after you zoom in or out with `cmd + +` or `cmd + -`. According to this GitHub [issue](https://github.com/koekeishiya/yabai/issues/28), this is not currently handled by yabai. However, we can use the following workaround as described by marcelja in the issue.

```
For iTerm2: In preferences --> general --> window:
Adjust window when changing font size could be disabled.
```