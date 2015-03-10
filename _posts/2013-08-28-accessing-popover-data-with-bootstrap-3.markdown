---
layout: post
status: publish
published: true
title: Accessing Popover Data with Bootstrap 3
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1636
wordpress_url: http://tosbourn.com/?p=1636
date: '2013-08-28 17:02:21 +0100'
date_gmt: '2013-08-28 16:02:21 +0100'
categories:
- Development Help
tags:
- Bootstrap
- Upgrade
- Namespacing
- Popover
comments:
- id: 398
  author: dAm2K
  author_email: dino@tuxweb.it
  author_url: ''
  date: '2014-02-03 17:07:00 +0000'
  date_gmt: '2014-02-03 16:07:00 +0000'
  content: thank you! Just saved my life.
- id: 644
  author: Magna
  author_email: magnafree2@gmail.com
  author_url: ''
  date: '2014-12-04 00:34:00 +0000'
  date_gmt: '2014-12-03 23:34:00 +0000'
  content: is there any possibility to retain the updated data? I mean like if you
    click on the button and popover shows up then enter some data and close it then
    click on it again and the updated data is there.
- id: 645
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-12-04 10:37:00 +0000'
  date_gmt: '2014-12-04 09:37:00 +0000'
  content: That would need to be handled by your popover. Either by redoing the query
    on show or by not destroying it on hide.
---
<p>I was banging my head against this today so I figured I would share to hopefully reduce someone's banging their head time by a few minutes.</p>
<p>One of the things Bootstrap has done as part of their upgrade is to namespace their stuff, this is a good thing but is a bit of an arse if you weren't expecting something to be renamed.</p>
<p>Case in point, this used to work in Bootstrap 2.x</p>
<pre><code>$('#my_awesome_element').data('popover');</code></pre>
<p>And this would return the popover element that is going to be created, as of Bootstrap 3 you have to write something like;</p>
<pre><code>$('#my_awesome_element').data('bs.popover');</code></pre>
<p>A simple change but one that (at the time of writing) wasn't documented anywhere that I could see.</p>
