---
layout: post
title: Key code for Command on OS X
categories:
- Javascript
tags:
- Mac
description: There are a couple of key codes for the OS X Command Key
---

In JavaScript you often went to detect keypresses, you can do this by listening to keydown or keyup events and seeing which key code.

    window.onkeydown = function(ev){ alert (ev.which) }

Will alert out the key code for each key on your keyboard as you press it.

What is interesting to note is that the CMD (command) key on the Mac seems to report a different key code depending on the browser.

* On Firefox it is 224
* On Safari and Chrome it is 91.

I thought this was pretty interesting.

