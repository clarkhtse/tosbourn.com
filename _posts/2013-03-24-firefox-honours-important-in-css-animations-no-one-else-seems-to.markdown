---
layout: post
status: publish
published: true
title: Firefox honours !important in CSS animations, no one else seems to
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1394
wordpress_url: http://tosbourn.com/?p=1394
date: '2013-03-24 18:15:32 +0000'
date_gmt: '2013-03-24 17:15:32 +0000'
categories:
- Development Help
tags: []
comments: []
---
<p>I came across an inconsistency recently when working with animations in CSS. If I have a property that is marked as <code>!important</code> browsers will ignore this when it comes to animation and animate anyway whereas Firefox will not animate any property that has been set to be important.</p>
<p>Here is a <a href="http://tosbourn.com/playground/important/" target="_blank">demo of Firefox honouring !important</a>, if you open this in Chrome and in Firefox you will see what I mean.</p>
<h2>Questions</h2>
<p>I think the first thing that this highlights is that using <code>!important</code> is a bad idea (there are loads of reasons why <code>!important</code> can really screw your day up, this is just one of them!)</p>
<p>The second thing is it begs the question, are Firefox doing it right or wrong? Maybe there is a reason why all other browsers handle this differently?</p>
<p>I think Firefox is doing it right in this instance, when you add <code>!important</code> to something you are effectively saying &mdash; I don't care about anything else, this element needs to have this property applied to it for now and forever.</p>
<h2>The 'Fix'</h2>
<p>I use the term Fix loosely because I am not convinced anything is broken, but there are two ways to make Firefox act like the other browsers;</p>
<ol>
<li>Don't use <code>!important</code> in your markup (this is my preferred option)</li>
<li>Use <code>!important</code> in your keyframes block</li>
</ol>
<h2>The Code</h2>
<p>The code I used to generate the demo can be found as a <a href="https://gist.github.com/tosbourn/5232678" target="_blank">gist</a>, or of course you could just view the source on the demo ;-)</p>
