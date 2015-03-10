---
layout: post
status: publish
published: true
title: Git command to show files changed in a commit
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 420
wordpress_url: http://www.tosbourn.com/?p=420
date: '2011-04-04 09:39:17 +0100'
date_gmt: '2011-04-04 08:39:17 +0100'
categories:
- Development Help
tags:
- Git
comments:
- id: 498
  author: Ahamed
  author_email: ahamed101@gmail.com
  author_url: ''
  date: '2014-06-12 17:47:00 +0100'
  date_gmt: '2014-06-12 16:47:00 +0100'
  content: Thanks for this!!
- id: 505
  author: Guest
  author_email: guest@guest.com
  author_url: ''
  date: '2014-06-30 10:37:00 +0100'
  date_gmt: '2014-06-30 09:37:00 +0100'
  content: Thanks it worked..
- id: 637
  author: Ravi
  author_email: mfsi.ravi@gmail.com
  author_url: ''
  date: '2014-11-19 13:02:00 +0000'
  date_gmt: '2014-11-19 12:02:00 +0000'
  content: thanks
---
<p>Recently I wanted to pull a list of changed files from an older commit from the command line.</p>
<p>Turns out (like most things in Git) this is very easy to do.</p>
<pre>git show --name-only {commit}</pre>
<p>You can replace {commit} with the SHA1 you want to retrieve, or things like HEAD or HEAD^^</p>
