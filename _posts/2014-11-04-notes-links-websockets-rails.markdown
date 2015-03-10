---
layout: post
status: publish
published: true
title: Some notes and links on websockets with rails
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2375
wordpress_url: http://tosbourn.com/?p=2375
date: '2014-11-04 17:56:31 +0000'
date_gmt: '2014-11-04 16:56:31 +0000'
categories:
- Development Help
tags:
- Rails
- WebSockets
comments: []
---
<p>I have been doing some research on getting WebSockets running with Rails.</p>
<p>I wanted to share some links and notes I have found/made to make it easier for folk who will be doing their own research at some time.</p>
<h2>ActionController::Live</h2>
<p>This is the new Rails 4 way of using sockets. Personally, I don't like the syntax we have to use for ActionController::Live</p>
<ul>
<li><a href="http://stackoverflow.com/a/22758142/197302">A discussion on Stack Overflow on if ActionController::Live is ready yet</a>. At the time of writing the consensus seems to be probably not.</li>
<li><a href="http://www.sitepoint.com/streaming-with-rails-4/">A guide to using ActionController::Live</a> if you wanted to have a play for yourself.</li>
</ul>
<h2>Websocket-Rails</h2>
<p>This is a gem for getting sockets running on rails. I like it, the syntax is nice and clean and can be extended to use Redis as a go between for any data.</p>
<ul>
<li><a href="https://github.com/websocket-rails/websocket-rails">The Websocket-rails repo</a>, complete with installation guide.</li>
<li><a href="http://websocket-rails.github.io/">The main website</a>, with more samples.</li>
</ul>
<h2>Other Solutions</h2>
<p>There are other ways of achieving this, using node is one way a lot of solutions go for using things like socket.io</p>
<ul>
<li><a href="http://liamkaufman.com/blog/2013/02/27/adding-real-time-to-a-restful-rails-app/">One way to use socket.io within Rails</a></li>
<li><a href="http://mikeatlas.github.io/realtime-rails/">A gem for socket.io support</a></li>
<li><a href="https://github.com/sockjs/sockjs-client">SockJS</a> - like Socket.io but not</li>
<li>There are some paid solutions (which I haven't looked at in any detail) <a href="http://pusher.com/">Pusher</a>, <a href="http://www.pubnub.com/">PubNub</a></li>
</ul>
<h2>Have you any experience?</h2>
<p>I would love to chat with anyone who has had any experience with this, any great gems or samples I should be looking at?</p>
