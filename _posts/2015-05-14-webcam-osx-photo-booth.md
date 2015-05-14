---
layout: post
title: You can’t use the webcam on OS X without having a Photo Booth Library?!?!
categories:
- WTF
tags:
- OSx
---

I noticed something crazy this evening when I was checking on my [working wall](http://workingwall.io) website, my webcam had stopped being picked up.

This machine is less than a year old, so I was very worried that there was some odd hardware fault. Turns out there isn’t anything wrong with it, I just had recently removed a folder in my `~/Pictures` directory called “Photo Booth Library”.

Crazy me thinking that the Photo Booth Library would effect the Photo Booth app and nothing else.

## Fixing a “broken” webcam on OS X

In order to test the webcam I decided to open up Photo Booth, the first thing I was greeted with was a message saying “Photo Booth could not locate your photo library”. Whilst this message was showing the light on my webcam was not on.

![Photo Booth Message]({{site.url}}/img/photo_booth_library.png)

I opted to “Create New...” and immediately noticed that the light came on my camera. I figured I would immediately refresh the website and sure enough my camera was spotted and working like normal.

## WTF Apple

Why on earth is Photo Booth an integral component needed to get the webcam working? Pictures taken on the webcam via a website don’t get stored to this library and from poking around this Photo Booth Library directory the only data I can see is a file that contains a handful of characters called `PkgInfo`.
