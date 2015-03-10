---
layout: post
status: publish
published: true
title: Setting up Apache on OSx Mountain Lion
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1102
wordpress_url: http://tosbourn.com/?p=1102
date: '2012-08-04 19:11:39 +0100'
date_gmt: '2012-08-04 18:11:39 +0100'
categories:
- Development Help
tags:
- Apache
- OSx
- Mountain Lion
comments: []
---
<p>I have always used <a href="http://www.apachefriends.org/en/xampp.html">XAMPP</a> on Windows machines and it comes with an OSx version so I have usually been lazy and just used it on any OSx installs I have had to use.</p>
<p>Recently though I have wanted finer control over my machines and part of that is to run anything as barebones as possible, which means not having something like XAMPP in the middle.</p>
<p>This guide assumes you are running OSx Mountain Lion and have xCode installed, it may work on older versions of OSx and may not require xCode, but honestly I don't have any other systems to test this on!</p>
<p>The guide is also only three steps step long, because with this set up Apache is already installed.</p>
<ol>
<li>Open your terminal.</li>
<li>Type <code>sudo apachectl start</code></li>
<li>Enter in your password.</li>
</ol>
<p>Now when you browse to http://localhost you should see an 'It works!' message.</p>
<p>To change the settings you should edit the file located at <code>/etc/apache/httpd.conf</code></p>
