---
layout: post
status: publish
published: true
title: What is the RAILS_GEM_VERSION
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1065
wordpress_url: http://tosbourn.com/?p=1065
date: '2012-07-09 16:53:56 +0100'
date_gmt: '2012-07-09 15:53:56 +0100'
categories:
- Other
tags:
- Ruby
- Rails
- RAILS_GEM_VERSION
comments: []
---
<p>Whilst trying to hunt down why a Rails app I was trying to rake wasn't playing ball I decided to go line by line through the config/environment.rb file.</p>
<p>The first non-commented line sets the RAILS_GEM_VERSION.</p>
<p>This is common to most Rails apps, and I have never thought to question it before, but now I need to be able to see were something is dying and every bit of knowledge helps!</p>
<p>So basically RAILS_GEM_VERSION highlights the version of Rails that should be used by an application. The reason this is important is because you can have multiple versions of Rails on your machine at any one time, and newer versions of Rails don't always play nicely with older ones, so having your app freeze on a particular version is good practice.</p>
