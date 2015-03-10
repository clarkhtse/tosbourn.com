---
layout: post
status: publish
published: true
title: Getting rid of annoying text selection at the bottom of Sublime Text documents
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1572
wordpress_url: http://tosbourn.com/?p=1572
date: '2013-06-26 15:46:33 +0100'
date_gmt: '2013-06-26 14:46:33 +0100'
categories:
- Development Help
tags:
- Sublime Text 2
- Text Selection
- Bug
- Fix
comments:
- id: 199
  author: Rob
  author_email: speaktorob@gmail.com
  author_url: ''
  date: '2013-08-16 16:16:00 +0100'
  date_gmt: '2013-08-16 15:16:00 +0100'
  content: Yes! Massive thanks.
- id: 201
  author: Ian
  author_email: ian@obermillers.com
  author_url: ''
  date: '2013-08-18 22:30:00 +0100'
  date_gmt: '2013-08-18 21:30:00 +0100'
  content: Perfect, thank you!
- id: 369
  author: Gabriel
  author_email: doesnt@matter.com
  author_url: ''
  date: '2014-01-09 14:27:00 +0000'
  date_gmt: '2014-01-09 13:27:00 +0000'
  content: Thanks! :D
- id: 407
  author: Matt
  author_email: usc11@live.com
  author_url: ''
  date: '2014-02-14 23:19:00 +0000'
  date_gmt: '2014-02-14 22:19:00 +0000'
  content: Awesome, thanks for this tip!
- id: 610
  author: Colin
  author_email: colin.g.sanford@gmail.com
  author_url: ''
  date: '2014-09-13 18:29:00 +0100'
  date_gmt: '2014-09-13 17:29:00 +0100'
  content: This has been driving me nuts. Thank you so much!
---
<p>If you use Sublime for prolonged periods of time I am sure you will have occasionally noticed that if you try and select or click on some code near the bottom of the screen Sublime will sometimes select all the code from the last line to where you have clicked.</p>
<p>This is incredibly annoying, luckily there is a quick solution for it - <strong>VIM</strong> (just kidding).</p>
<p>If you open your User Preferences file and add in the following;</p>
<p><code>"scroll_past_end": true</code></p>
<p>This will stop the selection from happening - this also means your file will keep scrolling down when you get to the bottom, in practice this doesn't bother me at all and the fact text doesn't get selected incorrectly now more than makes up for this.</p>
