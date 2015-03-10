---
layout: post
status: publish
published: true
title: MySQLTuner - An excellent free MySQL tool
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 552
wordpress_url: http://tosbourn.com/?p=552
date: '2011-09-12 21:28:22 +0100'
date_gmt: '2011-09-12 20:28:22 +0100'
categories:
- Development Help
tags:
- MySQL
- Linux
- Profiler
- Perl
comments:
- id: 48
  author: Brent W Peterson
  author_email: creativedata@gmail.com
  author_url: http://twitter.com/brentwpeterson
  date: '2011-09-15 14:54:00 +0100'
  date_gmt: '2011-09-15 13:54:00 +0100'
  content: |-
    Toby, I am having trouble with this value

    Variables to adjust:    query_cache_limit (&gt; 24G, or use smaller result sets)

    I have 32gb on my server
- id: 49
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-09-15 16:55:00 +0100'
  date_gmt: '2011-09-15 15:55:00 +0100'
  content: "I would suggest giving 25G a try.  \n\nYou want to get as much out of
    it as possible but at the same time you don't want to have to overload your RAM
    so you end up reading from the disk lots.\n\nThe trick with the profiler is to
    adjust the values and give it a day or two of use before re-profiling.  And back
    up your my.cnf before every change ;-)"
- id: 50
  author: Brent W Peterson
  author_email: creativedata@gmail.com
  author_url: http://twitter.com/brentwpeterson
  date: '2011-09-15 17:13:00 +0100'
  date_gmt: '2011-09-15 16:13:00 +0100'
  content: Cheers Toby!
- id: 137
  author: OpenSimFan
  author_email: ''
  author_url: http://twitter.com/OpenSimFan
  date: '2012-05-21 23:17:00 +0100'
  date_gmt: '2012-05-21 22:17:00 +0100'
  content: 'how do this on Windows? '
- id: 138
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-05-22 08:34:00 +0100'
  date_gmt: '2012-05-22 07:34:00 +0100'
  content: I can't see a way of getting it to work on Windows sorry.
---
<p><a title="MySQL Tuner" href="http://mysqltuner.pl/" target="_blank">MySQLTuner</a> is a fairly small perl script that you can run on the linux box that contains your MySQL setup.</p>
<p>It (very quickly) checks your configuration and produced an actionable report of recommendations.</p>
<p>Naturally as it is only a script you shouldn't just blindly follow exactly what it recommends, but it did point out some glaring omissions in one of my setups and it will certainly give you some food for thought.</p>
<p>Running the script is very easy, to get everything setup you run through the following steps;</p>
<ol>
<li>Grab the script - wget mysqltuner.pl*</li>
<li>Set permissions on it to allow you to execute it - chmod +x mysqltuner.pl</li>
<li>Run it - ./mysqltuner.pl</li>
</ol>
<p>* This works because the owner owns the domain mysqltuner.pl, it was a very clever idea since perl scripts are commonly given the extension .pl</p>
<p>Given how quick it is to install and run I am not sure why you wouldn't give it a go (unless you have invested in another similar solution)</p>
