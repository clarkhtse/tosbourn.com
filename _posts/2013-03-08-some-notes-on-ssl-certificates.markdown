---
layout: post
status: publish
published: true
title: Some Notes on SSL Certificates
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1336
wordpress_url: http://tosbourn.com/?p=1336
date: '2013-03-08 11:20:32 +0000'
date_gmt: '2013-03-08 10:20:32 +0000'
categories:
- Other
tags:
- SSL
comments: []
---
<p>Here are some selected notes regarding SSL Certificates, this is more of a brain dump than anything so your mileage with this post may vary.</p>
<ul>
<li>You should take the time to learn the theory behind private/public key authentication, knowing why you are doing something will always make it easier to get to grips with the practical aspects of it. <a href="http://security.stackexchange.com/questions/6737/what-is-an-ssl-certificate-intended-to-prove-and-how-does-it-do-it">Stack Exchange has a nice question on it</a> and <a href="http://en.wikipedia.org/wiki/Public-key_cryptography">here is a Wikipedia article</a>;</li>
<li>If your hosting company offers to install SSL, don't be a hero, let them.</li>
<li>If your server has cPanal/Webmin/Some form of admin that has SSL stuff, don't be a hero, use it. (mainly because if you manually change stuff some of their scripts might change it back)</li>
<li>You should where possible follow the advice laid out by the SSL issuer you are buying from, some of them have different preferences for how the .csr file is generated and it would just be quicker then sending them the wrong stuff.</li>
<li>Speaking of <a href="http://en.wikipedia.org/wiki/Certificate_signing_request">.csr file</a> - this is a certificate signing request, it is basically a file you send to an SSL issuer saying "This is who I am, please verify me thank you"</li>
<li>The command to generate the .csr is something like; <strong>openssl req -nodes -newkey rsa:2048 -keyout myserver.key -out server.csr</strong></li>
<li>The .key file above is your private key, keep that safe (seriously)</li>
<li>Where files should sit depends mainly on your configuration and server setup, a quick google will answer any questions.</li>
<li>Depending on the SSL certificate you are asking for authentication can take a while and may involve some offline steps - plan accordingly if you are planning a launch.</li>
</ul>
