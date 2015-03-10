---
layout: post
status: publish
published: true
title: Netbeans Private Key Authorisation Problem
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 555
wordpress_url: http://tosbourn.com/?p=555
date: '2011-09-15 11:24:13 +0100'
date_gmt: '2011-09-15 10:24:13 +0100'
categories:
- Development Help
tags:
- PuTTY
- Netbeans
- sFTP
comments:
- id: 157
  author: angeloghiotto
  author_email: angeloghiotto@gmail.com
  author_url: ''
  date: '2013-05-24 20:39:00 +0100'
  date_gmt: '2013-05-24 19:39:00 +0100'
  content: Thank You Very Much !!!
- id: 167
  author: kaaskop
  author_email: kaaskop@vpx.co.za
  author_url: ''
  date: '2013-06-19 23:13:00 +0100'
  date_gmt: '2013-06-19 22:13:00 +0100'
  content: Thanks! saved me few hours!
- id: 207
  author: Grabix
  author_email: tgrabowski87@gmail.com
  author_url: ''
  date: '2013-08-27 09:38:00 +0100'
  date_gmt: '2013-08-27 08:38:00 +0100'
  content: Thanks
- id: 214
  author: Marta
  author_email: nie@podam.com
  author_url: ''
  date: '2013-09-21 11:58:00 +0100'
  date_gmt: '2013-09-21 10:58:00 +0100'
  content: Me to, a lot :)
- id: 489
  author: ybmgryzzz
  author_email: ybmgryzzz@gmail.com
  author_url: ''
  date: '2014-05-27 15:34:00 +0100'
  date_gmt: '2014-05-27 14:34:00 +0100'
  content: Thanks very much Toby ... Was trying to work on this for NPP and worked
    as well.
- id: 564
  author: Nathon Fuller
  author_email: nathon.fuller@gmail.com
  author_url: ''
  date: '2014-08-27 23:18:00 +0100'
  date_gmt: '2014-08-27 22:18:00 +0100'
  content: Awesome! quick google search succeeded once more
---
<p>Recently I ran into an issue with key based authentication between Netbeans and an sFTP server.  It was returning an error saying I had an invalid private key.</p>
<p>The key worked for other tools, so I was slightly confused why it wouldn't for Netbeans.</p>
<p>After some digging I uncovered that Netbeans doesn't like PPK files, it needs OpenSSH key files in order to connect with key based authentication</p>
<p>The fix is pretty simple;</p>
<ol>
<li>Download <a href="http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html" target="_blank">PuTTY Key Generator</a>.</li>
<li>Open your PPK file. (<strong>File &gt; Load Private Key</strong>)</li>
<li>Convert your file. (<strong>Conversions &gt; Export OpenSSH Key</strong>)</li>
<li>Load this as your key file in Netbeans.</li>
</ol>
