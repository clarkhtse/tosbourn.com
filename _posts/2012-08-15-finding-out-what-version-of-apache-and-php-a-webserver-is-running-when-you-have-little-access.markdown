---
layout: post
status: publish
published: true
title: Finding out what version of Apache and PHP a webserver is running when you
  have little access
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1109
wordpress_url: http://tosbourn.com/?p=1109
date: '2012-08-15 13:37:20 +0100'
date_gmt: '2012-08-15 12:37:20 +0100'
categories:
- Development Help
tags:
- PHP
- Apache
- curl
- quick-tip
comments: []
---
<p>There are better ways to do this, but let us assume you have no access via SSH or even FTP to be able to add a file.</p>
<h2>Linux / OSx</h2>
<p>Open up a terminal window and type the following;</p>
<p><code>curl --head http://thesite.com</code></p>
<p>This will return something similar to:</p>
<pre><code>HTTP/1.1 200 OK
Date: Wed, 15 Aug 2012 10:41:32 GMT
Server: Apache/2.2.9 (Debian) PHP/5.3.8-1~dotdeb.1 with Suhosin-Patch
X-Powered-By: PHP/5.3.8-1~dotdeb.1
Set-Cookie: PHPSESSID=47d6a5e22c54307f211f67294f17495f; path=/
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
Pragma: no-cache
Keep-Alive: timeout=15, max=100
Content-Type: text/html
Accept-Ranges: none
Connection: Keep-Alive
</code></pre>
<p>And as you can see in this information you can find the Apache and PHP information.</p>
