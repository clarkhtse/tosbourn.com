---
layout: post
status: publish
published: true
title: Internet Explorer 8 Checkbox Issues
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 134
wordpress_url: http://www.tosbourn.com/?p=134
date: '2009-09-08 20:14:18 +0100'
date_gmt: '2009-09-08 19:14:18 +0100'
categories:
- Development Help
tags:
- Internet Explorer 8
- RLSB
- Martin Ivanov
- Checkbox
comments: []
---
<p>I think Internet Explorer 8 has improved upon Internet Explorer 7 in pretty much every way, everything just seems to run smoother on it and it supports things that Internet Explorer 7 wasn't great at.  It also helped to renew the importance of getting rid of Internet Explorer 6 and perhaps helped to drive a nail into the Internet Explorer 6 coffin.</p>
<p>However there is one thing that it has really taken a step back on and that is how checkboxes scale whenever you use the zoom tool in IE8.  I say 'how they scale' but the issue is actually that they just don't.</p>
<p>I have to admit this is something I normally wouldn't be that worried about, I mean the scaling works grand in pretty much every other browser, and what users really scale sites anyway?</p>
<p>Visually impaired users, that's who!  And it was whilst working on a site specifically aimed at people with a visual impairment that this issue cropped up.  All of the input fields scaled fine using a variety of in built and third party tools expect for checkboxes and radio buttons in Internet Explorer 8.</p>
<p>It was actually Dave Arthur from the <a href="http://www.rlsb.org.uk/">Royal London Society for the Blind</a> who came up with the solution, or more accurately came up with a <a href="http://acidmartin.wordpress.com/2009/07/17/using-css-to-style-radiobuttons-and-checkboxes-for-safari-and-chrome/">link to the solution</a>.</p>
<p>For those of you who don't want to read it, basically the fix is to use CSS sprites with an image that has checkbox and radio button images on it, then you can apply these images to the offending elements, whenever the page scales now, the image scales up normally and no functionality is lost.</p>
<p>I have mentioned a <a href="http://www.tosbourn.com/2009/08/browser-history-fix-ajax/">post</a> by Martin Ivanov before, and hopefully this second post will help persuade people that this man knows his stuff and that you should subscribe to <a href="http://acidmartin.wordpress.com/">his blog</a>!</p>
