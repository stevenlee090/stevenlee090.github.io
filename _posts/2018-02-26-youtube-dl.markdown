---
title: "youtube-dl plugin"
layout: post
date: 2018-02-26 10:04
image: /assets/images/iterm.png
headerImage: false
tag:
- youtube
- download
- utility
star: false
category: blog
author: stevenlee
description: The best plugin for downloading youtube content.
---

I have always wanted to find ways to easily extract non-copyrighted content off youtube (e.g. my own videos, royalty free music and so on). When I first attempted this, I installed some random youtube downloader software, but did not realise that it was filled with advertisements and installed a search bar add-on to my browser. The software was mediocre, did what it was supposed to do, but the overall user experience was poor and prompted me to search for an alternative.

I eventually came across [youtube-dl on GitHub](https://github.com/rg3/youtube-dl#installation) which is an amazing package which turned out to be the best youtube downloader I have ever used.

---

## How to setup youtube-dl

1. [Visit youtube-dl github page and see the installation section](https://github.com/rg3/youtube-dl#copyright)

2. If you are using a UNIX based machine and have `curl`, then proceed with the following block of code.
```
sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```
Mac users with [Homebrew](https://brew.sh/) by:
```
brew install youtube-dl
```

3. To enable the ability to download youtube videos as mp3 files, we need to install ffmpeg first. For mac users with brew, this can be done simply by:
```
brew install ffmpeg
```

4. Now you are ready to go!

---

## How to use youtube-dl

1. To download a video without any additional option, the linked content will be saved at a 720p video.
```
youtube-dl https://www.youtube.com/embed/dQw4w9WgXcQ
```

2. To download only the audio as mp3.
```
youtube-dl --extract-audio --audio-format mp3 https://www.youtube.com/watch\?v\=dQw4w9WgXcQ
```
