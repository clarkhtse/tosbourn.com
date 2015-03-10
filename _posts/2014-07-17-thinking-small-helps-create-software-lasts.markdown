---
layout: post
status: publish
published: true
title: Why thinking small helps create software that lasts.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2147
wordpress_url: http://tosbourn.com/?p=2147
date: '2014-07-17 16:53:05 +0100'
date_gmt: '2014-07-17 15:53:05 +0100'
categories:
- Other
tags:
- Chad Fowler
- Fred George
- Rails Israel
- Baruco
- Micro-Services
- Dublin Web Summit
comments: []
---
<p>Last year I attended the Dublin Web Summit, among some of the excellent talks were two by Chad Fowler and Fred George. I wanted to share them here and talk about why they are important.</p>
<h2>Fred George on Micro-Service Architecture</h2>
<p><iframe src="//www.youtube.com/embed/2rKEveL55TY" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen"></iframe></p>
<p>This video is from Baruco in 2012, but the content is pretty much identical to what was at the conference I attended.</p>
<p>In this talk Fred walks us through his learnings and thought process over many years as he attempted to implement Micro-Service architectures at various companies.</p>
<p>If you are not sure what a Micro-Service is don't worry, the video explains it very well, but if you want to read up a bit more on it I can recommend <a href="http://bit.ly/1qhS50Y" target="_blank">this post</a>.</p>
<p>One of the conclusions was that around <strong>100 lines is probably enough for most services</strong>, at this size rewrites become trivial and testing loses priority. There is only so much damage you can do in 100 lines of code.</p>
<p>One of the other conclusions was that if you have an architecture of potentially hundreds of tiny services is that integration testing starts to lose priority, <strong>a better solution is to monitor business metrics</strong>. If sales start to drop of a particular product it might be an indication that something isn't performing as it should be.</p>
<p>Having such small services allows for developers to more easily pick the correct tool for the job, the services are decoupled so you could easily write one thing in Ruby and another in Node.</p>
<h2>Chad Fowler on Disposable Components</h2>
<p><iframe src="//www.youtube.com/embed/7aGStT29fs0" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen"></iframe></p>
<p>Just like Fred's talk, this video isn't from the conference I attended but is a recording of an almost identical talk by Chad. This video is from Rails Israel in 2013.</p>
<p>The first portion of this talk by Chad explores why long lasting systems (think Unix and tools of that ilk) last and concludes that it is because they have <strong>small replaceable parts</strong>.</p>
<p>Chad draws similarities between the likes of classic cars and the human body, individual parts (cells) can be replaced constantly, but the sum of those parts remains.</p>
<p>The second portion goes into some rules that he has introduced at this company, for their detail watch the video but I will summarise their headlines here;</p>
<ol>
<li>Comments are a design smell</li>
<li>(Unit) Tests are a design smell</li>
<li>The System is heterogeneous by default.</li>
<li>Code has to be "this" big.</li>
<li>Nodes (servers) are disposable.</li>
<li>Never upgrade software on an existing node.</li>
<li>After you deploy a system, throw away the keys to it.</li>
<li>Always be deploying.</li>
<li>Assume failure.</li>
<li>Monitor everything.</li>
<li>Experience your worst case scenario so you don't have to fear it.</li>
<li>Data should be as small as possible.</li>
</ol>
<p>I want to quote from the talk;</p>
<blockquote><p>If your services are so small that you can read them in one go, you probably don't need a test.</p></blockquote>
<p>I think this is very powerful. If you start to refactor things to make them so small that you can understand their function in one read, you are surely testing the underlying language more than business logic.</p>
