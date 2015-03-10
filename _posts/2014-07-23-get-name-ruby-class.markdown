---
layout: post
status: publish
published: true
title: Get the name of a Ruby class
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2194
wordpress_url: http://tosbourn.com/?p=2194
date: '2014-07-23 22:04:45 +0100'
date_gmt: '2014-07-23 21:04:45 +0100'
categories:
- Development Help
tags:
- Ruby
comments: []
---
<p>Earlier today I wanted to get the name of a class in Ruby.</p>
<p>The reason I needed this was because I was grabbing an object that was polymorphic so I didn't really know what I was dealing with.</p>
<p>Here is how I did it with some help from ActiveSupport;</p>
<p><code>my_object.class.name.demodulize</code></p>
<p>my_object is the object that I was unsure about.</p>
<p>Calling <code>class</code> on it returns a Class object.</p>
<p>Calling <code>name</code> on that object returns the name of the class.</p>
<p>Calling <code>demodulize</code> is a nice way of removing any modules that happen to be before it (I didn't need the module information and most of the times you won't).</p>
<p>If you don't want to rely on ActiveSupport you can do;</p>
<p><code>my_object.class.name.split('::').last</code></p>
