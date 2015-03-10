---
layout: post
status: publish
published: true
title: Getting the flot-rails gem to play nicely with IE8
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1605
wordpress_url: http://tosbourn.com/?p=1605
date: '2013-07-24 10:15:43 +0100'
date_gmt: '2013-07-24 09:15:43 +0100'
categories:
- Development Help
tags:
- Internet Explorer 8
- JavaScript
- Ruby on Rails
- Flot
comments: []
---
<p><a href="http://www.flotcharts.org/">Flot</a> is a really useful graphing tool built on top of jQuery, and someone has very kindly created a rails gem called <a href="https://github.com/Vasfed/flot-rails">flot-rails</a> which allows you to easily include the relevant JavaScript files in your rails project.</p>
<p>An issue I found recently that was to allow flot to play nicely with IE8 you should have excanvas.js present, this essentially gives canvas support to older versions of Internet Explorer (which is something that flot relies on).</p>
<p>What the README file of the rails-flot gem doesn't explain well is that packaged up in the gem are all the JavaScript files you could need for flot, include excanvas.js</p>
<p>The fix then, if you are using rails-flot along with a need to support Internet Explorer 8 is to include the following in your manifest file;</p>
<p><code>//= require excanvas.js</code></p>
<p>Before you require anything relating to flot.</p>
