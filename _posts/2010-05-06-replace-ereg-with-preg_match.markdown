---
layout: post
status: publish
published: true
title: Replace ereg with preg_match
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 234
wordpress_url: http://www.tosbourn.com/?p=234
date: '2010-05-06 12:57:52 +0100'
date_gmt: '2010-05-06 11:57:52 +0100'
categories:
- Development Help
tags:
- PHP
- ereg
- preg_match
comments: []
---
<p>I was recently developing on a newer version of PHP than what is currently used on most of our servers and I was getting a warning telling me that the function ereg was depreciated.</p>
<p>A little googling told me that is is going to be totally removed from PHP 6 so in the interest of keeping my code nice and up to date I made the following changes....</p>
<p>Use preg_match instead of ereg and wrap the expression with //</p>
<p>Simple!</p>
<p>Here is an example;</p>
<blockquote><p>ereg("^[-]?[0-9]+([\.][0-9]+)?$", $var);</p></blockquote>
<p>Becomes</p>
<blockquote><p>preg_match("/^[-]?[0-9]+([\.][0-9]+)?$/", $var);</p></blockquote>
