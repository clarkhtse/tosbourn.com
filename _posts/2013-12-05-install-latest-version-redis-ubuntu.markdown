---
layout: post
status: publish
published: true
title: How to install the latest version of Redis on Ubuntu
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1750
wordpress_url: http://tosbourn.com/?p=1750
date: '2013-12-05 20:29:27 +0000'
date_gmt: '2013-12-05 19:29:27 +0000'
categories:
- Development Help
tags:
- Ubuntu
- Redis
- Install
comments:
- id: 441
  author: drazvan
  author_email: drazvan@gmail.com
  author_url: ''
  date: '2014-04-07 21:03:00 +0100'
  date_gmt: '2014-04-07 20:03:00 +0100'
  content: nice one man!
- id: 442
  author: Pramod
  author_email: pramod@joshsoftware.com
  author_url: ''
  date: '2014-04-08 08:55:00 +0100'
  date_gmt: '2014-04-08 07:55:00 +0100'
  content: nice guide to install redis
- id: 451
  author: Keith
  author_email: 780575b1@opayq.com
  author_url: ''
  date: '2014-04-25 15:21:00 +0100'
  date_gmt: '2014-04-25 14:21:00 +0100'
  content: Thanks for the really useful, concise instructions
- id: 542
  author: dennis
  author_email: muthuri_dennis@yahoo.com
  author_url: ''
  date: '2014-08-05 17:04:00 +0100'
  date_gmt: '2014-08-05 16:04:00 +0100'
  content: thanks
---
<p>I wish this was a one line post where I say type <code>sudo apt-get install redis-server</code>, and it *almost* is, but not quite.</p>
<p>OK so the above command will work and you will get a version of Redis installed on your machine, but it isn't a very recent version, this may or may not be enough for your needs, but I wanted to be able to pass in parameters when I start the server, this is something you can only do in more recent versions.</p>
<p>This is what you need to type, I will explain it after;</p>
<pre><code>$ sudo apt-get install -y python-software-properties
$ sudo add-apt-repository -y ppa:rwky/redis
$ sudo apt-get update
$ sudo apt-get install -y redis-server</code></pre>
<p>Line 1 - So we want to add a new repository that contains the latest version of Redis, the easiest way to do this requires <code>add-apt-repository</code>, which most likely isn't installed on your machine, so the first thing we want to do is install <code>python-software-properties</code>, this gives us access to add-apt-repository.</p>
<p>Line 2- Next we want to set up this new repository.</p>
<p>Line 3 - Now we want to update apt so it sees any changes we have made.</p>
<p>Line 4 - Finally we want to install <code>redis-server</code>, now the latest version will be installed.</p>
<p>If you are wondering the -y flag just saves me having to manually OK things I was going to OK anyways, this is really handy if you are running these steps as part of a provisioning step (which I was)</p>
