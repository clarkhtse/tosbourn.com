---
layout: post
status: publish
published: true
title: Permissions issue with Iomega Home Media Network Drive
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 861
wordpress_url: http://tosbourn.com/?p=861
date: '2012-02-22 00:11:17 +0000'
date_gmt: '2012-02-21 23:11:17 +0000'
categories:
- Other
tags:
- Iomega
comments:
- id: 161
  author: Andrew Kent Morris
  author_email: milsorgen@gmail.com
  author_url: ''
  date: '2013-06-08 20:29:00 +0100'
  date_gmt: '2013-06-08 19:29:00 +0100'
  content: Been having trouble with this myself, I've come across some write-ups on
    some of the higher end Iomega kit where they take out the drive and temporarily
    install it in a Linux box to manually set permissions. This is looking more and
    more like the only option.
- id: 162
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-06-09 10:32:00 +0100'
  date_gmt: '2013-06-09 09:32:00 +0100'
  content: |-
    Cheers for the heads up Andrew - I haven't had any bother with mine since but I will know for next time.


    Is there a guide or anything that you have found/followed that would be useful? If so I will certainly add it to the post and credit you with the spot.
---
<p>I recently purchased an Iomega Home Media Network Drive and whilst I am largely happy with it I had hit a few issues with sharing files between different users on the system and even different computers with the same user.</p>
<p>For some reason it would let the machine/user that uploaded the file access it completely but if another machine or user tried to get at it it would be in a read only state.</p>
<p>I tried to do some digging on the net but came up short so I started playing about with some settings.  It seems that turning the SSL security off did the trick. I have no idea why this would have broken anything in the first place but since my wireless network is already pretty safe I am happy if communications between my machines and the drive aren't encrypted.</p>
<p>I would like to turn the security settings back on at some point though, so if anyone finds a more permanent fix please let me know!</p>
