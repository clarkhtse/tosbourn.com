---
layout: post
status: publish
published: true
title: Internet Explorer Cannot Open The Internet Site - Operation Aborted
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 284
wordpress_url: http://www.tosbourn.com/?p=284
date: '2010-08-30 10:55:34 +0100'
date_gmt: '2010-08-30 09:55:34 +0100'
categories:
- Development Help
tags:
- JavaScript
- Internet Explorer
comments: []
---
<p>I found this error this morning after adding some JavaScript into a page.</p>
<blockquote><p>Internet Explorer Cannot Open The Internet Site ***** Operation Aborted</p></blockquote>
<p>Which I found more than a little odd since I was using some well supported jQuery that wasn't doing anything particularly fancy.</p>
<p>After a lot of Googling I found out that this is a known issue and Microsoft have issued some patches concerning it, but if you want to fix the issue across the board for IE you just need to add the following into your opening script tag.</p>
<blockquote><p><strong>defer='defer'</strong></p></blockquote>
<p>This basically will defer the execution of the script until the page has finished loading (something I didn't particularly want to happen but ho-hum!)</p>
