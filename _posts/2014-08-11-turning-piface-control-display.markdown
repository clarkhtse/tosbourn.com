---
layout: post
status: publish
published: true
title: Turning off the PiFace Control and Display
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2285
wordpress_url: http://tosbourn.com/?p=2285
date: '2014-08-11 16:42:37 +0100'
date_gmt: '2014-08-11 15:42:37 +0100'
categories:
- Development Help
tags:
- Raspberry Pi
- Python
- Element 14
- PiFace Control and Display
comments: []
---
<p>I have been playing with the <a href="http://www.element14.com/community/community/raspberry-pi/raspberry-pi-accessories/controlanddesign">PiFace Control and Display</a> and have been absolutely loving it. I will be posting up plenty more about it in the coming weeks.</p>
<p><a href="http://tosbourn.com/wp-content/uploads/2014/08/2014-08-11-16.33.57.jpg"><img class="aligncenter size-large wp-image-2286" src="http://tosbourn.com/wp-content/uploads/2014/08/2014-08-11-16.33.57-768x1024.jpg" alt="2014-08-11 16.33.57" width="474" height="632" /></a>I have noticed when I am using the Python library <a href="http://piface.github.io/pifacecad/reference.html">PiFaceCAD</a> and do something daft that makes the program exit incorrectly the LCD screen doesn't clean up after itself.</p>
<p>It feels like this would be a drain on battery and just knacker the hardware a bit quicker so I have written a quick <a href="https://github.com/tosbourn/turn-off-piface-control-and-display">Python script that will turn the LCD screen off</a>. You can run this if ever you notice your screen on when it shouldn't be.</p>
<p>&nbsp;</p>
