---
layout: post
status: publish
published: true
title: Show off your Localhost with LocalTunnel
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1654
wordpress_url: http://tosbourn.com/?p=1654
date: '2013-09-05 12:04:21 +0100'
date_gmt: '2013-09-05 11:04:21 +0100'
categories:
- Development Help
tags:
- Ruby
- Rubygems
- LocalTunnel
- Localhost
comments: []
---
<p>Today I had a need access my localhost from a device that was intentionally not on the same network, which meant I finally had a use case for playing about with <a href="http://progrium.com/localtunnel/">LocalTunnel</a>.</p>
<p>LocalTunnel is something I had heard of before but never really played with because I had no cause to, essentially it is a Ruby Gem that allows you to connect to your localhost on a specific port from a randomly assigned public address.</p>
<p>You install it the same way you would any gem;</p>
<pre><code>gem install localtunnel</code></pre>
<p>And you call it like this;</p>
<pre><code>localtunnel -k ~/.ssh/id_rsa.pub 3000</code></pre>
<p>Which gives it your public ssh key and tells it to bind to port 3000.</p>
<p>Once this is done LocalTunnel will spit out a URL which you can copy and paste to access your local machine from anywhere.</p>
<h2>Security Concerns?</h2>
<p>My first and primary worry about this is that I am putting a part of my local machine on the internet, that obviously isn't deadly but because it is bound to one particular port, so long as you maintain good security practice on the thing you are now sharing with the world then your dev box is no less secure than your server should be, but I wouldn't advise running LocalTunnel for longer than you need to, it certainly shouldn't be considered a permanent solution to anything.</p>
