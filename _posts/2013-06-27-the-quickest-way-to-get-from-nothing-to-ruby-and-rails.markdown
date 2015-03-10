---
layout: post
status: publish
published: true
title: The quickest way to get from nothing to Ruby and Rails
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1574
wordpress_url: http://tosbourn.com/?p=1574
date: '2013-06-27 23:08:03 +0100'
date_gmt: '2013-06-27 22:08:03 +0100'
categories:
- Development Help
tags:
- Ruby on Rails
- Setup
comments: []
---
<p>This is the quickest/easiest way I can see for someone running Mac OSx to get up and running with Ruby on Rails assuming they are starting with a blank slate.</p>
<p>Just dumping it here for future reference;</p>
<pre><code>curl -L https://get.rvm.io | bash
source "/Users/your-username/.rvm/scripts/rvm"
rvm get stable
rvm reload
rvm install 2.0.0 (this might take some time and you may need to enter your password a couple of times)
gem install rails</code></pre>
<p>Now you are ready to call <code>rails new my_awesome_app</code></p>
