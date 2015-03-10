---
layout: post
status: publish
published: true
title: Working with Ubunutu? Save yourself a headache and run sudo apt-get install
  build-essential
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1117
wordpress_url: http://tosbourn.com/?p=1117
date: '2012-09-20 12:01:50 +0100'
date_gmt: '2012-09-20 11:01:50 +0100'
categories:
- Other
tags:
- Ubuntu
- Linux
- C
comments: []
---
<p>If you are working with a clean install of Ubuntu and are trying to set up some sort of development environment you will almost definitely need to run <code>sudo apt-get install build-essential</code>.</p>
<p>The command installs the <a href="http://packages.ubuntu.com/quantal/build-essential">build-essential package</a> which amongst other things installs a C compiler, which you will almost certainly need because a lot of things in the GNU/Linux world are written in C.</p>
<p>Some tutorials will include this step (or bury the build-essential package in with a host of other packages to download) but many of them assume you must have already performed this step.</p>
