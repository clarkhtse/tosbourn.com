---
layout: post
status: publish
published: true
title: Updating PHP5.2 to PHP5.3 using apt-get
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 790
wordpress_url: http://tosbourn.com/?p=790
date: '2012-01-06 15:26:17 +0000'
date_gmt: '2012-01-06 14:26:17 +0000'
categories:
- Development Help
tags:
- PHP
- Server
comments: []
---
<p>There are already a couple of guides online already about this, but none of them seemed complete or at least I had to do some extra digging to solve things perhaps unique to my setup.</p>
<p>Here is what I have done to update PHP5.2 to PHP5.3 using apt-get;</p>
<p>You will need to execute the following commands as root or sudo them.</p>
<ol>
<li>Back everything up.</li>
<li>Make sure everything is backed up (seriously).</li>
<li>Add some lines to your sources list<br />
<strong>vi /etc/apt/sources.list</strong></p>
<pre># php5.3
deb http://php53.dotdeb.org oldstable all
deb-src http://php53.dotdeb.org oldstable all</pre>
</li>
<li>Request some public keys;<br />
<strong> gpg --keyserver keys.gnupg.net --recv-key 89DF5277 </strong><br />
<strong>gpg -a --export 89DF5277 | sudo apt-key add -</strong></li>
<li>Update your system<br />
<strong>apt-get update</strong><br />
<strong>apt-get dist-upgrade </strong></li>
<li>(optional, I had to do this for my GD library) update php5-gd<br />
<strong>apt-get -f install php5-gd</strong></li>
<li><span style="color: #000000;">Test your sites.</span></li>
<li><span style="color: #000000;">Take a new backup with your new setup.<br />
</span></li>
</ol>
