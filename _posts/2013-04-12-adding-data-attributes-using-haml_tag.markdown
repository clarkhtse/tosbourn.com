---
layout: post
status: publish
published: true
title: Adding Data Attributes using haml_tag
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1430
wordpress_url: http://tosbourn.com/?p=1430
date: '2013-04-12 16:34:21 +0100'
date_gmt: '2013-04-12 15:34:21 +0100'
categories:
- Development Help
tags:
- Ruby
- HAML
- haml_tag
comments: []
---
<p>Normally when using <code>haml_tag</code> you can add attributes by typing something like; <code>haml_tag :a, class: 'my-class'</code></p>
<p>Unfortunately because of the hyphen in data attributes the same pattern doesn't work if you try and add them, so <code>haml_tag :a, data-id: '5'</code> will crap itself.</p>
<p>What you can do though is call something like; <code>haml_tag :a, data: {id: '5'}</code> which will output the following HTML; <code>&lt;a data-id='5'&gt;&lt;/a&gt;</code></p>
<p>You can also add multiple data attributes like so; <code>haml_tag :a, data: {id: '5', type: 'arbitrary code'}</code> which is pretty handy.</p>
