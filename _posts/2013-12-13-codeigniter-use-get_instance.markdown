---
layout: post
status: publish
published: true
title: CodeIgniter - when to use get_instance()
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1768
wordpress_url: http://tosbourn.com/?p=1768
date: '2013-12-13 14:57:11 +0000'
date_gmt: '2013-12-13 13:57:11 +0000'
categories:
- Development Help
tags:
- CodeIgniter
comments:
- id: 371
  author: Om Betmen
  author_email: omadmin@mailbox.co.id
  author_url: ''
  date: '2014-01-16 10:33:00 +0000'
  date_gmt: '2014-01-16 09:33:00 +0000'
  content: what about the performance?
- id: 372
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-16 11:06:00 +0000'
  date_gmt: '2014-01-16 10:06:00 +0000'
  content: |-
    Hey there, cheers for commenting!

    So there is going to be an overhead associated with grabbing this object but I haven't noticed anything particularly slow and I don't believe there is a better way to get access to the functionality that it provides.
---
<p>If you are new to CodeIgniter you may be confused as to when you need to use <code>get_instance</code> and when you don't, it certainly tripped me up when I first came back to CodeIgniter after leaving the PHP community for some time.</p>
<p>Luckily it is pretty simple to remember.</p>
<p>If you are writing code that lives within a controller, a model or a view that is under CodeIgniter's control then you <strong>do not</strong> need to use <code>get_instance</code>.</p>
<p>If however you are writing your own custom libraries or something that sits outside of the MVC files then <strong>you do</strong> need to use it.</p>
<p>So, if you are inside a model you could do something like this;</p>
<pre><code>$this->load->library('my_cool_library')</code></pre>
<p>But if you are in a class you have written yourself then the $this object will not know about the CodeIgniter stuff, so you would do something like this;</p>
<pre><code>$ci=& get_instance();
$ci->load->library("my_cool_library")</code></pre>
<p>We use <code>=&</code> because we don't want to make a new copy of the CodeIgniter object, we want to use the original one.</p>
