---
layout: post
status: publish
published: true
title: 'Review: PiFace Control and Display'
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2319
wordpress_url: http://tosbourn.com/?p=2319
date: '2014-08-24 19:27:43 +0100'
date_gmt: '2014-08-24 18:27:43 +0100'
categories:
- Reviews
tags: []
comments: []
---
<p>Today I wanted to review the LCD screen I have for my Raspberry Pi, called the PiFace Control and Display. I received this at the same time that I got my <a title="Review: Raspberry Pi Camera Board" href="http://tosbourn.com/review-raspberry-pi-camera-board/">Raspberry Pi Camera</a>.</p>
<p>I got this from <a href="http://canada.newark.com/" target="_blank">Element14/Newark</a>.</p>
<p><a href="http://tosbourn.com/wp-content/uploads/2014/08/2014-08-11-16.33.571.jpg"><img class="aligncenter size-large wp-image-2321" src="http://tosbourn.com/wp-content/uploads/2014/08/2014-08-11-16.33.571-768x1024.jpg" alt="PiFace Control and Display" width="474" height="632" /></a></p>
<h2>Features of the PiFace Control and Display</h2>
<p>The reason I wanted an LCD screen is because a lot of the little projects I was doing on the Pi had the need of some basic way to show output to me. For example the output of a script or some basic status message.</p>
<p>The PiFace Control and Display does this and more, here is a rundown of some of the features;</p>
<ul>
<li>16 character by 2 line alphanumeric display</li>
<li>User definable custom characters</li>
<li>LED backlight</li>
<li>Infrared Receiver</li>
<li>3-position navigation switch</li>
<li>5 tactile switches</li>
<li>Python libraries provided</li>
</ul>
<h2>Installation of the PiFace Control and Display</h2>
<p>Physically installing this was very easy, the board fits over your GPIO pins (which, as a an aside, means that you can't use any of the pins for anything other than the LCD display).</p>
<p>Getting the display up and running from a software point of view was pretty easy too.</p>
<ol>
</ol>
<ol>
<li>You run <code>sudo raspi-config</code> to enter the main Raspberry Pi setup screen.</li>
<li>Select "Option 8 Advanced Options"</li>
<li>Choose the A5 SPI option, set this to</li>
<li>Select then .</li>
<li>Reboot your machine</li>
</ol>
<p>I did not have any infrared remotes that would let me play with the receiver, so I did not try and set this up.</p>
<p>To control the PiFace programmatically there are Python libraries, they are fairly well documented to get you started but are lacking community input to help expand on them.</p>
<h2>Thoughts  on the PiFace Control and Display</h2>
<p>Given how easy it is to get the basic input and output functionality working I would recommend this to anyone who either needs very simple input (including a basic form of list/character selection) or very simple output displayed.</p>
<h2>Uses for the PiFace Control and Display</h2>
<p>One of the things myself and a few people in <a href="http://rumblelabs.com">work</a> are excited about is using this as a basic score tracker for our table tennis matches, such a tracker has very basic input and output needs which makes the PiFace Control and Display a natural choice.</p>
<p>I have also hooked it up with my camera to do face detection and alert the LCD when a face is detected.</p>
<p>Finally, you could just use it to say hello to your twitter followers!</p>
<blockquote class="twitter-tweet" lang="en"><p>Hello Twitter! <a href="http://t.co/znOTXk4c3u">http://t.co/znOTXk4c3u</a></p>
<p>— Toby Osbourn (@tosbourn) <a href="https://twitter.com/tosbourn/statuses/498863607481110530">August 11, 2014</a></p></blockquote>
<p><script src="//platform.twitter.com/widgets.js" async="" charset="utf-8"></script></p>
