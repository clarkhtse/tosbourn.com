---
layout: post
status: publish
published: true
title: Installing PEAR for PHP on OSx
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1299
wordpress_url: http://tosbourn.com/?p=1299
date: '2013-02-05 23:07:19 +0000'
date_gmt: '2013-02-05 22:07:19 +0000'
categories:
- Development Help
tags:
- PHP
- OSx
- PEAR
comments:
- id: 467
  author: rasaiyanramesh
  author_email: rasaiyan.ramesh@gmail.com
  author_url: ''
  date: '2014-05-08 20:37:00 +0100'
  date_gmt: '2014-05-08 19:37:00 +0100'
  content: Good One... It was very useful for me..
---
<p>Along your PHP travels you will hear noises relating to installing something from PEAR to help you with some PHP snizz.</p>
<p>PEAR is simply a code repository, in fact PEAR stands for PHP Extension and Application Repository.</p>
<p>Installing it is a breeze assuming you already have php installed (you can verify this by typing <code>php -v</code> into your command line).</p>
<p>The first thing to check is that it isn't already installed — a quick command will verify; <code>pear version</code>. If this brings back version information then you are good to go, if it reports <code>Command not found</code> then follow these simple steps.</p>
<p>Download the phar file at this location: <a href="http://pear.php.net/go-pear.phar">http://pear.php.net/go-pear.phar</a></p>
<p>Run PHP on the file, so if you downloaded it to your Downloads folder then run <code>sudo php go-pear.phar</code>.</p>
<p>You will be asked some installation questions, I quite like the defaults but feel free to change whatever you want.</p>
<p>Next if you have accepted the defaults you will probably want to add PEAR to your path so that you can call it easily from the command line. I like to do this in vi but there are several ways to achieve it;</p>
<p>I run <code>sudo vi ~/.profile</code> and add in my PATH to the bottom of the document; <code>export PATH=/Users/YOUR_USER_NAME/pear/bin:$PATH</code>, I then reload my profile with <code>. ~/.profile </code> and that is me, now if I run <code>pear version</code> I get version information.</p>
