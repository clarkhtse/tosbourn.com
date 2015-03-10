---
layout: post
status: publish
published: true
title: Typeahead.js The Book!
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1613
wordpress_url: http://tosbourn.com/?p=1613
date: '2013-08-10 22:57:05 +0100'
date_gmt: '2013-08-10 21:57:05 +0100'
categories:
- Personal
tags:
- Book
- Typeahead.js
- Personal
- Writing
- Tim Trueman
- Veljko Skarich
- Jake Harding
comments:
- id: 198
  author: anonymous
  author_email: anonymous@gmail.com
  author_url: ''
  date: '2013-08-16 15:46:00 +0100'
  date_gmt: '2013-08-16 14:46:00 +0100'
  content: 'do you really think typeahead.js is general enough to write a whole book
    about it ? I think some of its abstractions are wrong (e.g.: ajax should not be
    part of the library) and for that reason we ditched it when choosing an autocomplete-tool
    for our software solution'
- id: 200
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-08-16 16:33:00 +0100'
  date_gmt: '2013-08-16 15:33:00 +0100'
  content: |-
    It isn't a general book on autocomplete tools though, it is specifically aimed at people wanting to use Typeahead.js, so in that sense it would be wrong for it to be too general. It is a short book all the same, because there isn't really that much to it!

    Regarding some of the design decisions made, I guess it depends on what you are already running, if you already require jQuery for other things then it makes sense for solutions to build upon it, but if you aren't already using jQuery then you are right, a more all encompassing solution would be better.

    Mind you, I would far more trust someone like jQuery to get Ajax right than I would someone who was just creating some Ajax solution just to live under the hood of this one thing.
- id: 217
  author: enrique
  author_email: enrique.78@gmail.com
  author_url: ''
  date: '2013-09-25 17:20:00 +0100'
  date_gmt: '2013-09-25 16:20:00 +0100'
  content: "toby\n\nbefore you get to involved in your book make sure you check alternative
    to typeahead as well. \n\nI stumbled on this github project https://github.com/lorenzoongithub/completely
    \n\nand thought it was an easier alternative to typeahead.js"
- id: 218
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-09-25 18:41:00 +0100'
  date_gmt: '2013-09-25 17:41:00 +0100'
  content: Thanks for your comment Enrique, but since the book is due out in the next
    couple of days I think I will plough on with it ;-)
- id: 338
  author: John Burns
  author_email: me@johnburns87.com
  author_url: ''
  date: '2013-12-18 09:57:00 +0000'
  date_gmt: '2013-12-18 08:57:00 +0000'
  content: Looking forward to it, congratulations!
- id: 339
  author: Barry Adams
  author_email: barry.adams@gmail.com
  author_url: http://www.barryadams.co.uk/
  date: '2013-12-18 10:00:00 +0000'
  date_gmt: '2013-12-18 09:00:00 +0000'
  content: Those saying "you shouldn't write a book about Typeahead.js, there are
    alternatives out there" sound a bit like someone saying "Arthur C Clarke shouldn't
    have written sci-fi, he could just as well have written about Soviet Russia."
    It's a total non-argument. Typeahead is out there, people use it a lot, and Toby
    wrote a book about it. And I reckon it's a fairly good one.
- id: 340
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-20 00:07:00 +0000'
  date_gmt: '2013-12-19 23:07:00 +0000'
  content: Thanks John!
- id: 341
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-20 00:07:00 +0000'
  date_gmt: '2013-12-19 23:07:00 +0000'
  content: Thanks for saying so Barry!
---
<p><img class="alignright size-full wp-image-1688" alt="typeahead" src="http://tosbourn.com/wp-content/uploads/2013/10/typeahead.png" width="175" height="213" />I have written a book on Typeahead.js, which you can buy the book from Amazon!</p>
<p><a href="http://www.amazon.co.uk/dp/1783282614/ref=as_li_ss_til?tag=tosbourn-21&amp;camp=2902&amp;creative=19466&amp;linkCode=as4&amp;creativeASIN=1783282614&amp;adid=02CGYN1VZQTKESQCJ9Q2&amp;&amp;ref-refURL=http%3A%2F%2Ftosbourn.com%2F">Buy from the UK</a><br />
<a href="http://www.amazon.com/gp/product/B00FFUL9PA/ref=as_li_ss_tl?ie=UTF8&amp;camp=1789&amp;creative=390957&amp;creativeASIN=B00FFUL9PA&amp;linkCode=as2&amp;tag=tosbourncom-20">Buy from the USA</a></p>
<p>For those who don't know <a href="http://twitter.github.io/typeahead.js/">Typeahead.js</a> is something created by the fine folks at Twitter that gives typeahead functionality to text input fields. It is really useful functionality and Tim Trueman, Veljko Skarich, Jake Harding, and co should be proud of their efforts.</p>
<p>For anyone interested the book will cover such things as;</p>
<ul>
<li>Installing Bower for Typeahead.js</li>
<li>Basic Searching using Typeahead.js</li>
<li>Preloading JSON</li>
<li>Fetch data from the server</li>
<li>Prefetching data with a server fallback</li>
<li>Manipulating data</li>
<li>Creating custom events</li>
<li>Collecting the dataset</li>
<li>Displaying your data to the user</li>
<li>Caching your results</li>
<li>Using LocalStorage</li>
<li>Minimizing lookups</li>
<li>Testing the Typeahead.js codebase</li>
<li>Testing your code that uses Typeahead.js</li>
<li>Integrating Typeahead.js into Bootstrap</li>
<li>Integrating Typeahead.js into WordPress</li>
<li>Integrating Typeahead.js with Ruby on Rails</li>
</ul>
