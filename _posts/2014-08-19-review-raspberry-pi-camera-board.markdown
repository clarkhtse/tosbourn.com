---
layout: post
status: publish
published: true
title: 'Review: Raspberry Pi Camera Board'
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2311
wordpress_url: http://tosbourn.com/?p=2311
date: '2014-08-19 20:31:00 +0100'
date_gmt: '2014-08-19 19:31:00 +0100'
categories:
- Reviews
tags: []
comments: []
---
<p>I wanted to write up a review of the Raspberry Pi Camera Board which I have been playing with for the last few weeks.</p>
<h2>Raspberry Pi Camera Board?</h2>
<p>Surely I mean like just a webcam right? Wrong! The Raspberry Pi comes with a slot (the CSI port) specifically to have something like a camera attached to it.</p>
<p>This means a couple of things;</p>
<ul>
<li><strong>No need to waste a precious USB slot on a camera.</strong> By default my model of the Pi only has 2 USB ports, permanently having a camera in one would be a big inconvenience.</li>
<li><strong>No need to worry about 3rd party drivers.</strong> Hardware support for cameras that connect this was is built into the Pi. To start using the camera you just need to connect it and enable it from your Pi settings page.</li>
</ul>
<p>If you are still confused maybe a picture will help :-)</p>
<p><a href="http://tosbourn.com/wp-content/uploads/2014/08/raspberry-pi-camera-module-300x225.jpg"><img class="aligncenter size-full wp-image-2313" src="http://tosbourn.com/wp-content/uploads/2014/08/raspberry-pi-camera-module-300x225.jpg" alt="raspberry-pi-camera-module-300x225" width="300" height="225" /></a></p>
<h2>What I got with my Camera</h2>
<p>I got the camera module from <a href="http://canada.newark.com/" target="_blank">Element14/Newark</a>. The camera comes as one unit, so as you can see in the picture above you get the camera, mounted to a small board and attached to it is a ribbon which you then attach to the CSI board.</p>
<h2>Installation Process</h2>
<p>The Installation Process was very straight forward, I followed the <a href="http://www.raspberrypi.org/help/camera-module-setup/">official guide</a> and was up and running in minutes.</p>
<h2>My thoughts on the Raspberry Pi Camera Board</h2>
<p>For the price (about £20) the camera is a <a href="http://www.element14.com/community/docs/DOC-54359/l/raspberry-pi-camera-board#anchor5">great spec</a>,  and installation was a breeze. The fact there are native Rasbian applications that talk directly to the camera is a huge plus and if you like coding in Python there are well documented libraries for that also.</p>
<p>I would happily recommend this camera to folk who own a Pi who either want  a new project to play with or have a specific use case in mind.</p>
<h2>Uses for the Camera</h2>
<p>One of the things I ended up doing with the camera is creating a small app that tried to detect faces and output that fact onto a small screen. If you like I can share the code with you in another post.</p>
<p>&nbsp;</p>
