---
layout: post
status: publish
published: true
title: CakePHP 2.0 Read Recursive
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 820
wordpress_url: http://tosbourn.com/?p=820
date: '2012-01-30 22:53:10 +0000'
date_gmt: '2012-01-30 21:53:10 +0000'
categories:
- Development Help
tags:
- CakePHP
comments:
- id: 105
  author: Aaron Peterson
  author_email: ''
  author_url: http://twitter.com/aaronlpeterson
  date: '2012-02-01 23:27:00 +0000'
  date_gmt: '2012-02-01 22:27:00 +0000'
  content: Check out the core behavior "Containable" as well.  It allows you to shape 
    your find results down to which fields are included.
- id: 106
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-02-01 23:41:00 +0000'
  date_gmt: '2012-02-01 22:41:00 +0000'
  content: Containable is indeed an excellent behavior - cheers for commenting.
- id: 448
  author: Gopal Aggarwal
  author_email: gopal1035@gmail.com
  author_url: http://www.gopal1035.info/
  date: '2014-04-16 07:22:00 +0100'
  date_gmt: '2014-04-16 06:22:00 +0100'
  content: Thank you.
---
<p>This is something that caught me out several times when I was new to CakePHP, so I thought I would post it here in case you are in a similar situation.</p>
<p>Basically I was hitting issues that when I was viewing the variables available to a view (using the CakePHP Debug Toolbar) were I was noticing that I was bringing back far more information than I needed (and occasionally, not enough)</p>
<p>Bringing back too much information is never a good thing, it is inefficient and a possible security leak.</p>
<p>The reason for this is that in CakePHP the <code>Read</code>, <code>Find</code> or <code>FindAll</code> takes in a value called <code>Recursive</code>.</p>
<p>To set the level of recursion you do something similar to the following;</p>
<pre><code>$this-&gt;Model-&gt;recursive = 1</code></pre>
<p>There are 4 settings, which can be read about in detail in the <a href="http://book.cakephp.org/2.0/en/models/model-attributes.html?highlight=recursive%20findall" target="_blank">CakePHP Book</a>, but basically you can use this to make <code>Read</code>, <code>Find</code> or <code>FindAll</code> not perform JOINS (or perform more of them!).</p>
<p>Be sure that your selections only ever return the data they need to and no more.</p>
