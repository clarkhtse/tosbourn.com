---
layout: post
status: publish
published: true
title: PHP Security - General PHP setup Gotchas
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 306
wordpress_url: http://www.tosbourn.com/?p=306
date: '2010-09-23 23:13:38 +0100'
date_gmt: '2010-09-23 22:13:38 +0100'
categories:
- Other
tags:
- PHP
- Security
- register_globals
- error_reporting
comments: []
---
<p>This is my first in a series of 9 posts dealing with PHP Security, my plan is to cover some of the broad topics associated with certain aspects of developing secure PHP applications in plain English.</p>
<p>Whilst I will be providing examples throughout I will not labour on certain points, I will however attempt to provide many sources that you can use to read up more on the various topics.</p>
<p>For this post I want to talk about some general PHP setup Gotchas that you might want to look out for.  There is a tendancy amongst some people (especially if they haven't had to install PHP) to assume that the default setting that their hosts provided them is the most secure.  There are three things wrong with thinking like that.</p>
<ol>
<li>It is lazy (and worst of all, boring)</li>
<li>The standard settings may not be the most secure for your setup.</li>
<li>Who said they gave you the standard settings?</li>
</ol>
<p>You should <strong>always</strong> check out your Apache/MySQL/PHP settings on any new server.</p>
<h3>Register Globals</h3>
<p>The first setting you should be looking up in php.ini is <strong>register_globals</strong> and making sure it is set to <strong>0</strong>.  This is the default setting but it is worth having a quick look because this little blighter could get you into a world of trouble (if you are a bad coder).</p>
<p>The reason I say if you are a bad coder is because there is nothing inherently wrong with having it turned on but if your code isn't tight enough then having register_globals on can let people type something like...</p>
<p><em><strong>http://yoursite.com/page.php?newVar=h@xx0r</strong></em></p>
<p>This <strong><em>newVar</em></strong> variable is now set in your code, it doesn't take a security expert to realise what crap that could land you in.</p>
<p>If you don't have access to the php.ini file on your server you can include that parameter in your .htaccess file that should be located in the root of your web folder. The line you would need to add is..</p>
<blockquote><p><strong>php_flag register_globals on</strong></p></blockquote>
<p>Whilst it is best practice to turn them off in order to try and keep your code a little less vulnerable you should really be turning on Error Reporting to point you in the right direction from time to time, which leads me very nicely onto my next heading...</p>
<h3>Error Reporting</h3>
<p>Error Reporting is concerned with what errors PHP will record, where it will store them, and if it will display them.  There are essentially four settings we should be concerning ourselves with, like with register_globals these can be set in php.ini, in a .htaccess file or in your php code.</p>
<ul>
<li><strong>error_reporting</strong> (Which I think should be set to <strong>E_ALL</strong> |<strong> E_STRICT</strong> *)</li>
<li><strong>display_errors</strong> (<strong>On</strong> for an internal DEV server or your home setup, <strong>Off</strong> for a client setup)</li>
<li><strong>log_errors</strong> (You should always have this set to <strong>On</strong>)</li>
<li><strong>error_log</strong> (You set this to where you want the logs to be stored eg <em>/location/to/log </em>**)</li>
</ul>
<p>*<strong>E_ALL</strong> in  basically means report everything, <strong>E_STRICT</strong> means be damned strict about it, errors and warnings alike will be picked up by PHP.</p>
<p>** Obviously your logs shouldn't be anywhere close to being inside the www folder, error notifications could really help a potential hacker.</p>
<p>You can set up your own error handling within PHP, but my suggestion would be use a framework to do this for you, only roll your own if you are confident in your abilities because if there is an error in your error handler, well...</p>
<h3>Closing Up</h3>
<p>You could write a small book on how to securely set up a server, and of course by the time you have written it the tips will be obsolete.  I will leave this post here with those 2 categories for now because these are the main ones that keep cropping up when people mention PHP setup and Security.</p>
<p>When I start writing my next post (entitled Forms and Filtering) there will be a lot more content to get your teeth into, because if you can write bullet proof code your app should be able to stand up on all but the most flaky of server setups!</p>
<h3>Resources</h3>
<ul>
<li><a href="http://blog.php-security.org/archives/3-register_globals-is-not-evil.html" target="_blank">Register Globals Is Not Evil</a></li>
<li><a href="http://en.wikibooks.org/wiki/PHP_Programming/Register_Globals" target="_blank">More Information On Register Globals</a></li>
<li><a href="http://php.net/manual/en/errorfunc.configuration.php" target="_blank">PHP's Error Configuration</a></li>
</ul>
<p><em>If you thought this post was in any way useful, please share it amongst others who you think would also benifit.</em></p>
