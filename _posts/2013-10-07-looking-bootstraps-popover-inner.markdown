---
layout: post
status: publish
published: true
title: Looking for Bootstrap's popover-inner?
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1685
wordpress_url: http://tosbourn.com/?p=1685
date: '2013-10-07 11:20:36 +0100'
date_gmt: '2013-10-07 10:20:36 +0100'
categories:
- Development Help
tags:
- CSS
- Bootstrap
- Popovers
comments:
- id: 638
  author: JewelleryMonthly
  author_email: dave@sorbetmedia.co.uk
  author_url: http://www.jewellerymonthly.com/
  date: '2014-11-21 11:49:00 +0000'
  date_gmt: '2014-11-21 10:49:00 +0000'
  content: |-
    .tooltip-inner {

      max-width: 200px;

      padding: 3px 8px;

      color: #fff;

      text-align: center;

      text-decoration: none;

      background-color: #000;

      border-radius: 4px;

    }
---
<p>If you have recently upgraded your version of Bootstrap from 2 to 3 then you might be wondering why some of your popovers are not working as you might expect.</p>
<p>One potential reason is that there used to be a class called <code>.popover-inner</code>, this now seems to be directly replaced with <code>.popover-content</code>.</p>
<p>I had some styled nested inside of <code>.popover-inner</code> which magically stopped applying after the update.</p>
