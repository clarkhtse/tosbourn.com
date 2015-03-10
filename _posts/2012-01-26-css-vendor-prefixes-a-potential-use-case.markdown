---
layout: post
status: publish
published: true
title: CSS Vendor Prefixes - A potential use case
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 814
wordpress_url: http://tosbourn.com/?p=814
date: '2012-01-26 11:31:27 +0000'
date_gmt: '2012-01-26 10:31:27 +0000'
categories:
- Other
tags:
- CSS
- Browsers
comments:
- id: 145
  author: Rory
  author_email: roryokane@yahoo.com
  author_url: http://roryokane.com/
  date: '2012-06-08 19:40:00 +0100'
  date_gmt: '2012-06-08 18:40:00 +0100'
  content: This raises the question, why do you want do give WebKit different styles
    in the first place? Are you sure that it is necessary? Maybe there is already
    an  way that you haven’t tried that works in all browsers. Or it is Webkit’s fault,
    but rather than letting you write WebKit-specific styles, WebKit should just fix
    whatever incompatibility is causing you to want them. We can’t tell which is the
    case unless you show us your code.
- id: 146
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-06-08 21:51:00 +0100'
  date_gmt: '2012-06-08 20:51:00 +0100'
  content: |-
    This is very true, and most of the time you are right, it is probably something that the browser or the developer has done wrong.

    I just think it would be neat for hacking on stuff.

    You could even then use CSS to use :before and :after to append vendor specific text/content.
---
<p>You know those moments when you know something won't work but you try it anyway just in case the web gods look favourably on you for once? Well I just had one of those and I would like to share it, because I think this is something that the web gods should consider.</p>
<p>Vendor prefixes in CSS serve the purpose of allowing browsers to play about with their own implementations of new CSS rules or adding stuff totally unique to them.</p>
<p>There have been arguments back and forward about how useful these are in production systems and there have been some great tools made to try and reduce how much time we spend in vendor prefix hell, personally I think anything that drives the web forward is a good thing and I think prefixes do that.  But anyway, enough pre-able.</p>
<p>What I would like to propose is that since we have vendor prefixes anyway, <strong>could we use them to target specific browsers with already known rules</strong>.</p>
<p>I have an edge case where it would be really nice to be able to do something like;</p>
<pre>margin-bottom: 59px;
-webkit-margin-bottom: 39px;</pre>
<p>What this would allow me to do is set the standard margin-bottom to 59px (if it not being 60px makes you twitch, join the club!) but in webkit browsers I would like the margin to be slightly smaller.</p>
<p>I know this could be misused and end in really sloppy, massive CSS files - but if used with care (which I promise I would do) it would be a neat way to achieve these odd little hacks that occasionally we need to do.</p>
