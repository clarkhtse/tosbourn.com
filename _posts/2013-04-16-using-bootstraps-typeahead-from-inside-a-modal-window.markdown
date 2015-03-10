---
layout: post
status: publish
published: true
title: Using Bootstrap's typeahead from inside a modal window
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1435
wordpress_url: http://tosbourn.com/?p=1435
date: '2013-04-16 16:29:06 +0100'
date_gmt: '2013-04-16 15:29:06 +0100'
categories:
- Development Help
tags:
- CSS
- Bootstrap
- Modal
- Facebox
comments:
- id: 168
  author: Mike Castro Demaria
  author_email: mcd@supersonique.net
  author_url: http://www.supersonique.net
  date: '2013-06-29 17:43:00 +0100'
  date_gmt: '2013-06-29 16:43:00 +0100'
  content: |-
    Simpler from boostrap issue number 1078:

    .typeahead.dropdown-menu { z-index: 200000; }
    .modal-body{overflow-y: inherit;}

    I hope this help,
    Mike
---
<p>If you want to use bootstrap's typeahead functionality from inside a modal window such as lightbox or facebox then you are probably going to have to make a small edit to one of the bootstrap files.</p>
<p>Open up <code>bootstrap-typeahead.js</code> in your text editor of choice and then add a <code>z-index</code> of 9999, like so;</p>
<pre><code>  this.$menu.css({
    top: pos.top + pos.height,
    left: pos.left,
    'z-index': 9999
  })</code></pre>
<p>You probably don't need to go as high as 9999 but it worked for me!</p>
<p>It took me way too long to get this working, other bootstrap things appear to work fine inside modals.</p>
