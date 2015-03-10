---
layout: post
status: publish
published: true
title: What you actually do when you untar something.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 280
wordpress_url: http://www.tosbourn.com/?p=280
date: '2010-08-26 10:54:42 +0100'
date_gmt: '2010-08-26 09:54:42 +0100'
categories:
- Development Help
tags:
- Command Line
- Linux
- tar
comments: []
---
<p>If you are anything like me you have typed more than your fair share of commands into Linux without actually knowing what you are passing in as parameters.  Over time you begin to learn a couple of them, but you are still largely just committing strings of text to memory.</p>
<p>One particularly potent example of this (for me) is the tar command.  I am frequently typing <strong>tar -xvzf myFiles.tar.gz</strong> and it works well, but I have no idea what the -xvzf was actually doing.  Until today when I bothered to find out and then blog about it!</p>
<p>So here are the commands and what they do;</p>
<ul>
<li>x - extract (makes sense, this is used because there is no untar function.)</li>
<li>v - verbose (ahh good old verbose, the one everyone knows, this will output the files tar extracts.)</li>
<li>z - filter the output through gzip (this is done as I have the .gz extension on most of my files.)</li>
<li>f - use archive file or device F (apparently, if anyone can explain this please post a comment.)</li>
</ul>
<p>For more information either run the man on tar or visit the <a href="http://unixhelp.ed.ac.uk/CGI/man-cgi?tar">man page for tar</a>.</p>
