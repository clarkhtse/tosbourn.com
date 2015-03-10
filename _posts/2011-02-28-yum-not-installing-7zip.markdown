---
layout: post
status: publish
published: true
title: Yum not installing 7zip.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 378
wordpress_url: http://www.tosbourn.com/?p=378
date: '2011-02-28 15:13:48 +0000'
date_gmt: '2011-02-28 14:13:48 +0000'
categories:
- Development Help
tags:
- Linux
- Yum
- 7zip
comments:
- id: 659
  author: Criação de Sites
  author_email: yvette_fullarton@gawab.com
  author_url: http://www.itnbi.com.br/desenvolvimento/
  date: '2015-01-01 14:57:10 +0000'
  date_gmt: '2015-01-01 13:57:10 +0000'
  content: "hello there and thank you for your info – I've certainly picked uup something
    \r\nneew from righht here. I did however expertise some technical issues using
    this site, since I experienced to reload the website \r\nlots of times previous
    to I could get it to load correctly.\r\n\r\nI had been wondering if your hosting
    iss OK? Not that I am complaining,\r\nbut slyggish loading instances times wikll
    sometimes affect your placemeent inn google and can dmage your high-quality score
    if ads and marketing with Adwords.\r\nAnyway I aam adding this RSS to myy email
    and cann look \r\nout for a lot more of your respective intriguing content.\r\n\r\nMake
    sure yyou update this again soon.\r\n\r\nHere is my web-site :: <a href=\"http://www.itnbi.com.br/desenvolvimento/\"
    rel=\"nofollow\">Criação de Sites</a>"
---
<p>Earlier I had an issue with yum not installing 7zip (or indeed anything) on a CentOS machine. I was trying to run;</p>
<blockquote><p>sudo yum install p7zip</p></blockquote>
<p>The fix (provided by <a href="http://twitter.com/braziel" target="_blank">@braziel</a>) was to run the following 4 lines of code, which seem to update yum effectively.</p>
<blockquote><p>wget http://packages.sw.be/rpmforge-release/rpmforge-release-0.5.2-2.el5.rf.i386.rpm<br />
rpm --import http://apt.sw.be/RPM-GPG-KEY.dag.txt<br />
rpm -K rpmforge-release-0.5.2-2.el5.rf.*.rpm<br />
rpm -i rpmforge-release-0.5.2-2.el5.rf.*.rpm</p></blockquote>
