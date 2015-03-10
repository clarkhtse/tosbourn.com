---
layout: post
status: publish
published: true
title: Allowing your own From header with sSMTP
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 282
wordpress_url: http://www.tosbourn.com/?p=282
date: '2010-08-26 12:46:23 +0100'
date_gmt: '2010-08-26 11:46:23 +0100'
categories:
- Development Help
tags:
- PHP
- Linux
- sSMTP
- Email
comments:
- id: 68
  author: wadexyz
  author_email: ''
  author_url: http://twitter.com/wadexyz
  date: '2011-11-09 03:58:00 +0000'
  date_gmt: '2011-11-09 02:58:00 +0000'
  content: beautiful
---
<p>Today I was wrestling with some email issues on a server and decided to install sSMTP as opposed to Sendmail for sending email out to their internal SMTP server.</p>
<p>First thing I should say is that installing it was a real dream compared to the messing around I had previously done with Sendmail and whilst I know it is no longer maintained it seems very solid and does exactly what I need it to.</p>
<p>One thing that perplexed me however was that whilst I was able to change most of the normal headers by simply passing them in using the PHP <strong>mail</strong>() function I was unable to set the 'From: ' header.</p>
<p>Since sSMTP uses the www-data user when it is running this is who was coming up as the sender, which is very ugly and not very helpful to the user.</p>
<p>Luckily there is a one line fix for this problem, in the ssmtp.conf file (found in my system at <em>/usr/local/etc/ssmtp/ssmtp.conf</em>) add the following line.</p>
<p><strong>FromLineOverride=YES</strong></p>
<p>This will then allow PHP to set whatever From header it wants.</p>
