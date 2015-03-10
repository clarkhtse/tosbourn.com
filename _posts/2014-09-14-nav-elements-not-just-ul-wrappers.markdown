---
layout: post
status: publish
published: true
title: Nav Elements, not just ul wrappers
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2337
wordpress_url: http://tosbourn.com/?p=2337
date: '2014-09-14 22:20:48 +0100'
date_gmt: '2014-09-14 21:20:48 +0100'
categories:
- Development Help
tags:
- Semantics
- Nav
comments:
- id: 614
  author: Derek Johnson
  author_email: derekmj74@gmail.com
  author_url: ''
  date: '2014-09-15 08:24:00 +0100'
  date_gmt: '2014-09-15 07:24:00 +0100'
  content: |-
    Nice post, and thanks for the menshie :)

    I would say it's still fine to markup the text in a paragraph elements (or several paragraphs) and wrap that in a nav, for the same reason as we use a list rather than styled spans for a more traditional navigation.

    No right or wrong, but I think your home page is still a paragraph, it's just inside a nav rather than replaced by one.
---
<p>In a recent tweet my good buddy <a href="/tag/derek-johnson/">Derek Johnson</a> pointed out an example of nav element usage that I could apply to my <a href="/">homepage</a>.</p>
<blockquote class="twitter-tweet" lang="en"><p><a href="https://twitter.com/tosbourn">@tosbourn</a> Check the last example for &lt;nav&gt; at <a href="http://t.co/bIorzgdENT">http://t.co/bIorzgdENT</a>. I was thinking your home page is a good candidate for that.</p>
<p>— Derek Johnson (@derekjohnson) <a href="https://twitter.com/derekjohnson/status/510324141216792577">September 12, 2014</a></p></blockquote>
<p><script src="//platform.twitter.com/widgets.js" async="" charset="utf-8"></script></p>
<p>To quote the article;</p>
<blockquote><p>A nav element doesn't have to contain a list, it can contain other kinds of content as well. In this navigation block, links are provided in prose</p></blockquote>
<p>I had never considered this use case before, it makes perfect sense!</p>
<p>I don’t want to speak on behalf of all developers (the time will come when I will, don’t worry) but personally speaking I have been following the letter of most of the HTML5 element’s specs but not really the spirit of them. I have learned one or two uses for each one and stuck rigidly to those.</p>
<p>When I think of the nav element I almost immediately think of the collection of unordered links at the top of my site. This is thinking visually about markup and it is short sighted.</p>
<p>The way I should be thinking is with the information, <strong>I should be asking what information am I conveying and what is the appropriate way to represent that information</strong>. It shouldn’t matter if that information is at the top of my page or in the middle of an article.</p>
<p>If I had thought like that from the start my homepage would never have been a paragraph element, I wasn’t conveying a paragraph of text, I was conveying links in long form.</p>
<p>I can hear some say, but Toby, who cares, the paragraph element works for a block of text just fine.</p>
<p>So does a div element, doesn't mean you should start using them instead of p elements.</p>
<p>Semantics are important, they are what tells machines (browsers/screen readers/website scrapers/etc) how to interpret the data you have presented them with.</p>
<p>Thanks so much to Derek for showing me this.</p>
