---
layout: post
status: publish
published: true
title: Killing all instances of Ruby on Rails running on a certain port.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1565
wordpress_url: http://tosbourn.com/?p=1565
date: '2013-06-12 10:12:21 +0100'
date_gmt: '2013-06-12 09:12:21 +0100'
categories:
- Development Help
tags:
- Server
- Ruby on Rails
- Console
- '3000'
comments: []
---
<p>I was having a hard time getting my Rails webserver to restart after it having a bit of a hissy fit. The process to handle most apps when this happens is to locate the PID (Process ID) of the thing that is broken and kill it.</p>
<p>An easy way to do this with Rails is to type the following into your Terminal;</p>
<p><code>lsof -wni tcp:3000</code></p>
<p>Which looks for all processes running on port 3000 (the most common port for things like Webrick and Thin to run on) and returns them all as a table.</p>
<p>One of the columns of the table will be the PID for the process, copy it and paste it into the following line which will go into your Terminal;</p>
<p><code>kill -9 PID</code></p>
<p>Replacing 'PID' with the PID you just copied.</p>
<p>This will kill all processes relating to that PID, once this is done you should be good to go ahead and restart your rails server.</p>
