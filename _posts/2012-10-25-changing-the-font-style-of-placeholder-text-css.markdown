---
layout: post
status: publish
published: true
title: Changing the font-style of placeholder text CSS
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1142
wordpress_url: http://tosbourn.com/?p=1142
date: '2012-10-25 15:33:38 +0100'
date_gmt: '2012-10-25 14:33:38 +0100'
categories:
- Development Help
tags:
- CSS
- HTML5
comments: []
---
<p>Note: This post could also be called, why I am an idiot and need to look for simple answers.</p>
<p>I needed to make my placeholder text italic in a project I was working on recently.</p>
<p>Initially I figured because this is a relatively new HTML5 attribute the CSS is probably going to involve some crazy CSS vendor prefixes, and the first path I went down confirmed this.</p>
<p>To change the colour of your placeholder text you need to use something like <code>input:-moz-placeholder {color:red;}</code> so I figured I would stick in <code>input:-moz-placeholder {font-style: italic}</code>, this didn't work and I couldn't figure why - obviously vendor prefixed solutions are never 100% and I initially started looking to double check Mozilla hadn't ripped this out or replaced it in newer versions of FireFox.</p>
<p>Then it dawned on me that it probably inherits some properties from its parent (input), so the change turned out to be incredibly simple: <code>input {font-style:italic}</code> did the trick.</p>
<p>There are two reasons why I didn't immediately come up with this solution.</p>
<ol>
<li>In my head I had already started over-complicating it.</li>
<li>The designs presented to me had only placeholder text, so I wasn't thinking about how to style the input, just how to style the placeholder.</li>
</ol>
<p>My lesson here is to not over think things too early on, try and find the simple solution first.</p>
