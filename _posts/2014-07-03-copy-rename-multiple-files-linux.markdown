---
layout: post
status: publish
published: true
title: Copy and Rename multiple files in Linux
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2090
wordpress_url: http://tosbourn.com/?p=2090
date: '2014-07-03 15:54:07 +0100'
date_gmt: '2014-07-03 14:54:07 +0100'
categories:
- Development Help
tags:
- Linux
- Copy
- sed
- rename
comments: []
---
<p>I am pasting this here for my own reference!</p>
<pre><code>for i in `ls files-to-copy-*`; do cp $i `echo $i | sed "s/rename-from/rename-to/g"`; done</code></pre>
<p>What this does is takes each file that is returned of the result of your <code>ls</code> command and pipes it do <code>sed</code>.</p>
<p>This sed command then looks for the part you want to rename and does it ("s/rename-from/rename-to/g" is a regular expression)</p>
