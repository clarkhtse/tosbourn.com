---
layout: post
status: publish
published: true
title: 'Get rid of var $name in CakePHP '
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 765
wordpress_url: http://tosbourn.com/?p=765
date: '2011-12-07 11:35:02 +0000'
date_gmt: '2011-12-07 10:35:02 +0000'
categories:
- Development Help
tags:
- CakePHP
comments:
- id: 91
  author: Euromark
  author_email: euromark@web.de
  author_url: http://www.dereuromark.de
  date: '2011-12-11 01:15:00 +0000'
  date_gmt: '2011-12-11 00:15:00 +0000'
  content: For 2.0 it is already removed everywhere. So no issues there anymore :)
- id: 92
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-12-11 01:46:00 +0000'
  date_gmt: '2011-12-11 00:46:00 +0000'
  content: "It still persists in many samples online, which is understandable but
    as I say I think it could throw new folk off a bit. \nCheers,\nToby"
- id: 93
  author: Euromark
  author_email: euromark@web.de
  author_url: http://www.dereuromark.de
  date: '2011-12-11 11:19:00 +0000'
  date_gmt: '2011-12-11 10:19:00 +0000'
  content: you are right - some code has still to be modified. but that will happen
    pretty soon. but I am not sure that is the reason people confuse the conventions.
    in the model the name is correctly singularized. either way - it has to go ;)
    I wrote a shell replacement script which did the job for my 2xxx files in less
    than 20 seconds :)
---
<p>A lot of people new to CakePHP struggle with remembering what to call and when, a common thing I see people doing inside their controller is something like;</p>
<p><code>$this-&gt;Sections-&gt;recursive = 0;</code></p>
<p>When actually they mean something like;</p>
<p><code>$this-&gt;Section-&gt;recursive = 0;</code></p>
<p>I think the reason the Model is sometimes pluralised is because when you look at most examples of how to write controllers the very first thing inside the class is;</p>
<p><code>var $name = 'Sections';</code></p>
<p>The reason this is included in both the Model and the Controller is to punch PHP4 into playing nice. If you require PHP4 then fair enough, but the vast majority of us use PHP5 and as such have no need for $name. So I would implore you to remove it from samples and code that doesn't require it as some people seem to trip up over it.</p>
