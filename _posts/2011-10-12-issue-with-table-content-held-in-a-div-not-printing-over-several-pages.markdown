---
layout: post
status: publish
published: true
title: Issue with table content held in a div not printing over several pages
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 603
wordpress_url: http://tosbourn.com/?p=603
date: '2011-10-12 21:15:32 +0100'
date_gmt: '2011-10-12 20:15:32 +0100'
categories:
- Development Help
tags:
- CSS
- Printing
- Table
comments: []
---
<p>Some time ago I had an issue with some table content not printing if the table filled up several pages, I asked about it on <a href="http://stackoverflow.com/questions/4315206/table-content-held-within-a-div-will-not-print-over-several-pages/4316333#4316333" target="_blank">Stack Overflow</a> but ended up working it out for myself.</p>
<p>You can read the full question and answer on the site, but essentially I needed to add;</p>
<p><code>* { overflow:visible ! important; }</code></p>
<p>into my stylesheet.</p>
