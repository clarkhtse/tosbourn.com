---
layout: post
status: publish
published: true
title: The safest way to track goal URLs in Google Analytics
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2056
wordpress_url: http://tosbourn.com/?p=2056
date: '2014-06-10 21:57:21 +0100'
date_gmt: '2014-06-10 20:57:21 +0100'
categories:
- Development Help
tags:
- Google Analytics
comments: []
---
<p>I was recently digging into some analytics and I wondered why a goal I was tracking had stopped working, I decided to do some digging.</p>
<p>Turns out that I was looking for a page being hit with my destination being set to "<strong>Equals to</strong>" and passing in the page I was expecting. For example;</p>
<p>Destination URL Equals To: <code>/thank-you-for-your-order/</code></p>
<p>For ages this worked like a charm, but recently the task that would send people to that page started adding some extra parameters to the URL, so the URL getting hit was <code>/thank-you-for-your-order/?foo=bar</code>.</p>
<p>This does not trigger my event because <code>/thank-you-for-your-order/?foo=bar</code> ≠ <code>/thank-you-for-your-order/</code></p>
<p>The safer thing to do is actually something that to some folk my appear scary, that is to use the Regular Expression option.</p>
<h2>Changing Equals To to Regular Expression in Google Analytics</h2>
<p>For something simple like my use case the conversion is painfully simple, I needed to change to Regular Expression and change the input to;</p>
<p><code>^\/thank-you-for-your-order\/</code></p>
<p>The ^ says the following stuff needs to appear at the start of the URL and all the \ is doing is letting the Regular Expression know to not treat the / as anything special and that it is part of the string we care about.</p>
<p>If you want to convert yours and are having a hard time please just leave a comment and I can take a look!</p>
