---
layout: post
status: publish
published: true
title: Accessing PHP variables from within JavaScript under WordPress
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 523
wordpress_url: http://tosbourn.com/?p=523
date: '2011-08-22 20:36:36 +0100'
date_gmt: '2011-08-22 19:36:36 +0100'
categories:
- Development Help
tags:
- Wordpress
- PHP
- JavaScript
comments:
- id: 173
  author: bigflannel
  author_email: mike@bigflannel.com
  author_url: ''
  date: '2013-07-08 21:58:00 +0100'
  date_gmt: '2013-07-08 20:58:00 +0100'
  content: Thank you. I searched and searched for this.
- id: 174
  author: bigflannel
  author_email: mike@bigflannel.com
  author_url: ''
  date: '2013-07-08 21:58:00 +0100'
  date_gmt: '2013-07-08 20:58:00 +0100'
  content: Thank you. I searched and searched for this.
- id: 552
  author: Felix Eve
  author_email: dahousecat@gmail.com
  author_url: ''
  date: '2014-08-15 07:59:00 +0100'
  date_gmt: '2014-08-15 06:59:00 +0100'
  content: Where is an appropriate place to put this code? I want to create a js variable
    in the backend on an admin page so am using add_filter('admin_head' however it
    is not working for me.
- id: 553
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-08-15 10:19:00 +0100'
  date_gmt: '2014-08-15 09:19:00 +0100'
  content: I didn't have to, although that post was written about three years ago
    so it could be that is the case now :-) Thanks for sharing the link!
---
<p>Accessing PHP variables from within JavaScript under WordPress is so easy it is almost trivial.  Having said that, I didn't know there was a way to do it until I <a href="http://wordpress.stackexchange.com/questions/26570/javascript-helpers" target="_blank">asked on the Wordpress StackExchange site</a>.</p>
<p>I will show you what you need to do by way of an example.  Let us suppose we need the site URL in our JavaScript code.</p>
<p>It is a two step process, the first step is in your PHP;</p>
<pre>wp_enqueue_script('my_script');
$data = array('site_url' =&gt; __(site_url()));
wp_localize_script('my_script', 'php_data', $data);</pre>
<p>So what we have done there is enqueued our script (named here, my_script) and once we have done that we set up our data array. In our case the property is site_url and it's contents are going to be the result of site_url(). Once we have that we can call wp_localize_script, into it we pass the name of our script, the name we want to give our JavaScript object and the data we want to pass in.</p>
<p>Next we want to be able to access the data, so in your JavaScript file you can simply call the following (if you wanted to alert out the site URL!)</p>
<pre>alert(php_data.site_url);</pre>
<p>Really, really easy and really, really handy!</p>
<p>For more information please see the <a title="Function Reference" href="http://codex.wordpress.org/Function_Reference/wp_localize_script" target="_blank">official reference</a>.</p>
