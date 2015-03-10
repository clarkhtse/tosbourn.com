---
layout: post
status: publish
published: true
title: Sublime Text reading SASS files as HAML
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1427
wordpress_url: http://tosbourn.com/?p=1427
date: '2013-04-11 14:57:57 +0100'
date_gmt: '2013-04-11 13:57:57 +0100'
categories:
- Development Help
tags:
- Sublime Text 2
- HAML
- SASS
- Syntax
comments:
- id: 171
  author: ian_989
  author_email: ian989@gmail.com
  author_url: ''
  date: '2013-07-01 13:12:00 +0100'
  date_gmt: '2013-07-01 12:12:00 +0100'
  content: Thanks Toby, I have been having this exact problem.
- id: 172
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-07-01 13:13:00 +0100'
  date_gmt: '2013-07-01 12:13:00 +0100'
  content: Glad I could be of help!
- id: 212
  author: Erniiiv
  author_email: benedikt.sattler@gmail.com
  author_url: ''
  date: '2013-09-20 13:44:00 +0100'
  date_gmt: '2013-09-20 12:44:00 +0100'
  content: There's a better way to do this, than messing with the haml package. Just
    open a sass file, view &gt; syntax &gt; open all with current extension as...
    SASS.
- id: 213
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-09-20 16:02:00 +0100'
  date_gmt: '2013-09-20 15:02:00 +0100'
  content: |-
    Thanks for the comment!



    That works too, but this is adding an extra layer on top and the underlying issue (that the HAML language settings try and grab SASS files as well) still persists.

    Normally I am against editing packages, but I think in this instance it makes sense.
- id: 283
  author: Gabo Lugo
  author_email: glsmaster.xg@gmail.com
  author_url: ''
  date: '2013-11-16 02:01:00 +0000'
  date_gmt: '2013-11-16 01:01:00 +0000'
  content: Amazing! Thanks a lot!
- id: 439
  author: Guest
  author_email: anonymized-1321950654@disqus.com
  author_url: ''
  date: '2014-04-07 04:17:00 +0100'
  date_gmt: '2014-04-07 03:17:00 +0100'
  content: +1Thanks!
- id: 440
  author: Roman Sotnikov
  author_email: roman.sotnikov@gmail.com
  author_url: ''
  date: '2014-04-07 04:17:00 +0100'
  date_gmt: '2014-04-07 03:17:00 +0100'
  content: Thanks!
---
<p>If this is happening for you and you want to fix it the quickest way do do this is to edit <code>Ruby Hamil.tmLanguage</code> on Mac OS X this can be found at the following location: <code>/Library/Application Support/Sublime Text 2/Packages/Rails/Ruby Haml.tmLanguage</code>.</p>
<p>Once you have it open look for the line <code>&lt;string&gt;sass&lt;/string&gt;</code> and delete it.</p>
<p>As soon as you save the document it should no longer associate SASS files as HAML, now this isn't the case the SASS syntax should take over (assuming you have downloaded it).</p>
