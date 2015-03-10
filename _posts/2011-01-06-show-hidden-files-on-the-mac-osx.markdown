---
layout: post
status: publish
published: true
title: Show hidden files on the Mac OSx
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 362
wordpress_url: http://www.tosbourn.com/?p=362
date: '2011-01-06 09:55:30 +0000'
date_gmt: '2011-01-06 08:55:30 +0000'
categories:
- Development Help
tags:
- Mac
- OSx
- hidden
comments: []
---
<p>Cheers to <a href="http://twitter.com/JonathanKelly50">Jonathan</a> for this one;</p>
<p>In the terminal type</p>
<pre>defaults write com.apple.finder AppleShowAllFiles TRUE</pre>
<p>Then</p>
<pre>killall Finder</pre>
