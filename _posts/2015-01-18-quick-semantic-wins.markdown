---
layout: post
status: publish
published: true
title: Quick Semantic Wins
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2486
wordpress_url: http://tosbourn.com/?p=2486
date: '2015-01-18 18:17:09 +0000'
date_gmt: '2015-01-18 17:17:09 +0000'
categories:
- Development Help
tags:
- Semantics
- '365'
comments:
- id: 682
  author: Derek Johnson
  author_email: derek@nostrongbeliefs.com
  author_url: ''
  date: '2015-01-19 23:33:00 +0000'
  date_gmt: '2015-01-19 22:33:00 +0000'
  content: Nice article and kudos for digging up the vein schema. Just one small point,
    the number input can take any integer not just whole numbers. Use the step attribute
    to find tune e.g. step="0.01" would be suitable for currencies and if you don't
    set a min="0" you can go into negative numbers.
- id: 683
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-01-20 01:38:00 +0000'
  date_gmt: '2015-01-20 00:38:00 +0000'
  content: Good shout – I have actually used that in the past, no idea why I wrote
    "whole numbers" I did just mean numbers. :-/
---
<p>Trying to make the jump from not really caring about semantics in your website to doing it 100% correctly can seem like a massive and daunting undertaking.</p>
<p>It doesn't have to be, with baby steps you can slowly get a feel for certain things that you can learn off which will get you on the way to using semantic elements and attributes correctly.</p>
<p>This is by no means a comprehensive list of things but like I say, just some good starting points.</p>
<h2>Some HTML elements and attributes to be aware of</h2>
<p>HTML5 has been the standard for some time now and has pretty much full support amongst the browsers, there are a host of great new elements that really help to define content better than a plain old <code>&lt;div&gt;</code> can.</p>
<p>Here are four common things that will be on your website at any given time that often are not semantically marked up.</p>
<ul>
<li>Your navigation areas should be a <a href="http://www.w3.org/html/wg/drafts/html/master/sections.html#the-nav-element"><code>&lt;nav&gt;</code></a>, this isn't just limited to the menu at the top of your screen but could be in your footer or even a paragraph of text whose soul purpose is to aid you in navigating to other areas.</li>
<li>Captioning an image should be done with <a href="http://www.w3.org/html/wg/drafts/html/master/grouping-content.html#the-figure-element"><code>&lt;figure&gt;</code></a> and <a href="http://www.w3.org/html/wg/drafts/html/master/grouping-content.html#the-figcaption-element"><code>&lt;figcaption&gt;</code></a>, in fact captioning anything should be captured in this way.</li>
<li>When citing something it is best practice to include the quote within <a href="http://www.w3.org/html/wg/drafts/html/master/grouping-content.html#the-blockquote-element"><code>&lt;blockquote&gt;</code></a> and within that include the citation inside <a href="http://www.w3.org/html/wg/drafts/html/master/text-level-semantics.html#the-cite-element"><code>&lt;cite&gt;</code></a></li>
<li>When accepting numbers in a form use <a href="http://www.w3.org/TR/html-markup/input.number.html"><code>&lt;input type="number" /&gt;</code></a> this has the added effect of allowing people to use the up and down arrows to increment and decrement their choice.</li>
</ul>
<h2>Some Schema to be aware of</h2>
<p>I am a big fan of <a href="http://schema.org">schema.org</a>, it has been adopted as the standard for several semantic tools including Google when it visits and scrapes your site for content. Here are some of my most used schemas.</p>
<ul>
<li>A blog post should use the <a href="http://schema.org/Blog">Blog schema</a>.</li>
<li>If you are reviewing something you should use the <a href="http://schema.org/Review">Review schema</a>.</li>
<li>A comment section can be marked up with the <a href="http://schema.org/UserComments">UserComments schema</a>.</li>
<li>If you happen to be talking about them, there is even <a href="http://schema.org/Vein">a schema for veins!</a> (I haven't actually ever used this!)</li>
</ul>
<h2>Some ARIA roles to be aware of</h2>
<p>ARIA roles are to be used when the meaning of an element isn't self evident. For example before we had the <code>&lt;nav&gt;</code> element you could have used <code>&lt;ul role="navigation"&gt;</code> to say that this was a navigational element.</p>
<p>Here are some of the more common roles that you can use without too much additional thought.</p>
<ul>
<li>If you have a search form on your site you should mark it up with <code>&lt;<a href="http://www.w3.org/TR/wai-aria/roles#search">form role="search"</a>&gt;</code></li>
<li>If you have an alert appear on screen that doesn't require any additional input from the user you should mark it as such. <code>&lt;<a href="http://www.w3.org/TR/wai-aria/roles#alert">div role="alert"</a>&gt;</code></li>
<li>If for some terrible reason you have a carousel on your website (don't have a carousel on your website) you should mark it up with <code>&lt;<a href="http://www.w3.org/TR/wai-aria/roles#marquee">div role="marquee"</a>&gt;</code></li>
</ul>
<h2>A quick disclaimer at the end!</h2>
<p>If you view the source of this page I am likely making some of the mistakes which I have said should be avoided – this site is on my list of things to fix!</p>
