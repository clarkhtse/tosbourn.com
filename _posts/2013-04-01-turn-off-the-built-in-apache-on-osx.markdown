---
layout: post
status: publish
published: true
title: Turn Off the built in apache on OSx
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1403
wordpress_url: http://tosbourn.com/?p=1403
date: '2013-04-01 07:30:37 +0100'
date_gmt: '2013-04-01 06:30:37 +0100'
categories:
- Development Help
tags:
- Apache
- Terminal
- OSx
comments:
- id: 294
  author: Jeremy
  author_email: mjjgillbanks@hotmail.com
  author_url: ''
  date: '2013-12-03 20:48:00 +0000'
  date_gmt: '2013-12-03 19:48:00 +0000'
  content: Thanks for explaining! Super clear and insightful.
- id: 359
  author: FMMachold
  author_email: machold@machold.ca
  author_url: ''
  date: '2014-01-02 14:54:00 +0000'
  date_gmt: '2014-01-02 13:54:00 +0000'
  content: Why?
- id: 360
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-02 14:56:00 +0000'
  date_gmt: '2014-01-02 13:56:00 +0000'
  content: One reason I want to is because I use Vagrant that wants to use the same
    ports that my local apache install uses and I don't want to have to run into the
    issue with my local apache turning itself on for whatever reason and killing my
    connection to Vagrant.
- id: 361
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-02 14:56:00 +0000'
  date_gmt: '2014-01-02 13:56:00 +0000'
  content: Glad it was useful to you Jeremy :-)
- id: 427
  author: Geoff Bowers
  author_email: modius@daemon.com.au
  author_url: http://www.daemon.com.au/
  date: '2014-03-10 11:51:00 +0000'
  date_gmt: '2014-03-10 10:51:00 +0000'
  content: Thanks Toby. How would you turn it back on again in the event that you
    wanted it back?
- id: 428
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-03-10 21:42:00 +0000'
  date_gmt: '2014-03-10 20:42:00 +0000'
  content: Great question Geoff, honestly I don't know because I have never looked
    back :-)
- id: 434
  author: James McWhorter
  author_email: james@jamesmcwhorter.com
  author_url: ''
  date: '2014-03-22 15:33:00 +0000'
  date_gmt: '2014-03-22 14:33:00 +0000'
  content: Excellent tip.  Thanks!  I was just setting Mamp Pro 3 and I kept running
    into a message telling me to turn off the built-in Apache server.
- id: 550
  author: Steffen Bilde
  author_email: steffenbilde@gmail.com
  author_url: http://steffenbilde.com/
  date: '2014-08-14 18:35:00 +0100'
  date_gmt: '2014-08-14 17:35:00 +0100'
  content: Thank you Toby! - This one saved my life!:)
- id: 551
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-08-14 18:39:00 +0100'
  date_gmt: '2014-08-14 17:39:00 +0100'
  content: Glad it helped :-)
- id: 560
  author: Elvis Priestly
  author_email: pekkle@ntlworld.com
  author_url: ''
  date: '2014-08-20 23:57:00 +0100'
  date_gmt: '2014-08-20 22:57:00 +0100'
  content: I tried using the built in Apache but it was getting in the way. MAMP seems
    simpler and I am using that. Thanks for the tip on how to stop the other Apache.
- id: 567
  author: Eduardo
  author_email: defreitasdudu@gmail.com
  author_url: ''
  date: '2014-09-02 16:38:00 +0100'
  date_gmt: '2014-09-02 15:38:00 +0100'
  content: switch 'unload for the 'load' keyword :p
- id: 692
  author: Noob
  author_email: semester0005@gmail.com
  author_url: ''
  date: '2015-02-07 09:44:00 +0000'
  date_gmt: '2015-02-07 08:44:00 +0000'
  content: God Bless You!
---
<p>There are a handful of reasons why you would want to turn off the built in apache on OSx, you might have installed your own version, maybe you don't use apache and it is interfering with something else, whatever the reason there is one command you need to run to turn it off.</p>
<pre><code>sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist</code></pre>
<p>You should run that from Terminal.app</p>
<p>I wanted to take a second to explain what is going on because too often people (myself included) will post a code snippet without explaining what it is, the worrying this is so many people run them without checking what is happening.</p>
<p><code>sudo</code> tells your computer to run the following command as the root (administrator) account.<br />
<code>launchctl</code> is an OSx program that interfaces with <code>launchd</code>, which is a daemon manager. Daemons are small programs that run as background processes (like what would setup Apache).<br />
unload tells launchctl to unload a specified configuration file.<br />
<code>-w</code> tells <code>launchctl</code> to override a disabled key, basically this will force the file to be marked as disabled.<br />
<code>/System/Library/LaunchDaemons/org.apache.httpd.plist</code> is the file that we are unloading.</p>
<p>Hopefully that helps!</p>
