---
layout: post
status: publish
published: true
title: Finding your SQL Server Version
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 291
wordpress_url: http://www.tosbourn.com/?p=291
date: '2010-09-17 15:58:08 +0100'
date_gmt: '2010-09-17 14:58:08 +0100'
categories:
- Development Help
tags:
- SQL Server
comments: []
---
<p>One of our clients in the company I work for is running SQL Server 2000, how do I know this wonderful bit of information you ask? Well, let me tell you;</p>
<blockquote><p>SELECT @@VERSION AS theVersion</p></blockquote>
<p>This took longer than 30 seconds to work out, which is frankly too long, so hopefully I will save someone else the pain when trying to work out what version you are running when you have limited privileges.</p>
<p>I ran this in the MASTER database, I am not sure if this is required though.</p>
