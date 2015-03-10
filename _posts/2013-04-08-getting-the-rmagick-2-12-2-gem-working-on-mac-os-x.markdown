---
layout: post
status: publish
published: true
title: Getting the rmagick 2.12.2 gem working on Mac OS X
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1424
wordpress_url: http://tosbourn.com/?p=1424
date: '2013-04-08 09:33:52 +0100'
date_gmt: '2013-04-08 08:33:52 +0100'
categories:
- Development Help
tags:
- Ruby
- Rubygems
- ImageMagick
- rmagick
comments:
- id: 211
  author: TK
  author_email: info@wireharbor.com
  author_url: ''
  date: '2013-09-17 18:45:00 +0100'
  date_gmt: '2013-09-17 17:45:00 +0100'
  content: You just saved me a ton of time fighting this issue. THANK YOU!
---
<p>So getting rmagick 2.12.2 working on Mac OS X isn't the easiest thing in the world, but it is possible.</p>
<p>The first thing I should say is that this assumes you already have ImageMagick installed on your machine, the second thing is that there is a rmagick 2.13.2 gem, which seems to work out of the box.</p>
<p>In my case I couldn't use 2.13.2 so I had to get things working with 2.12.2.</p>
<p>If you Google this issue there are loads of solutions out there, unfortunately all the low hanging fruit didn't work for me, these are things like;</p>
<ul>
<li><span style="line-height: 14px;">Making sure ImageMagick is installed</span></li>
<li>Telling the ruby gem where ImageMagick lives with <code>-- --with-opt-dir</code></li>
</ul>
<p>Thanks to <a href="https://coderwall.com/p/wnomjg">this link</a> I was able to get it sorted.</p>
<p>Here is a dump of the fix that you type into the terminal;</p>
<pre><code>cd /usr/local/Cellar/imagemagick/6.8.0-10/lib
ln -s libMagick++-Q16.7.dylib   libMagick++.dylib
ln -s libMagickCore-Q16.7.dylib libMagickCore.dylib
ln -s libMagickWand-Q16.7.dylib libMagickWand.dylib</code></pre>
