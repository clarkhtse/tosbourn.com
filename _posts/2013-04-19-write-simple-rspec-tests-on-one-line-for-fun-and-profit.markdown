---
layout: post
status: publish
published: true
title: Write simple rspec tests on one line for fun and profit
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1459
wordpress_url: http://tosbourn.com/?p=1459
date: '2013-04-19 10:54:00 +0100'
date_gmt: '2013-04-19 09:54:00 +0100'
categories:
- Development Help
tags:
- Ruby
- Ruby on Rails
- Rspec
comments: []
---
<p>If you have a test set up that performs one assertion then you can condense your test into one line, this makes things way more readable and shortens your tests.</p>
<p>For example:</p>
<pre><code>it "should return a response header with JSON in it" do
  response.header['Content-Type'].should include 'json'
end </code></pre>
<p>Can become:</p>
<pre><code>it { response.header['Content-Type'].should include 'json' }</code></pre>
<p>When you have lots of small tests like this it really helps to make your tests easier to read, which will in turn help you in keeping them up to date and sharing them with other people.</p>
