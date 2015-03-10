---
layout: post
status: publish
published: true
title: What the header element can be used for
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2437
wordpress_url: http://tosbourn.com/?p=2437
date: '2015-01-11 13:39:27 +0000'
date_gmt: '2015-01-11 12:39:27 +0000'
categories:
- Development Help
tags:
- Semantics
- Derek Johnson
- '365'
- Header
comments: []
---
<p>You might be thinking – obviously it is for the header of a page or section, end of article. It isn’t. I didn’t really think there were other uses for it until a conversation on Twitter with <a href="https://twitter.com/derekjohnson">Derek Johnson</a> last December.</p>
<p>I asked “What is the most semantic way to markup a tldr; section in HTML? aside? Is it just a paragraph of text?”</p>
<p>And he replied <a href="https://twitter.com/derekjohnson/status/546781671211929600">over two tweets</a></p>
<blockquote><p><code>&lt;header&gt;</code> or <code>&lt;footer&gt;</code>, <code>&lt;header&gt;</code> is for introductory content and <code>&lt;footer&gt;</code> is for information about the parent section(ing root).</p></blockquote>
<p>Thanks so much for that slap of semantic goodness Derek!</p>
<p>So, lets dig into this a bit more.</p>
<p><a href="http://www.w3.org/html/wg/drafts/html/master/sections.html#the-header-element">The spec</a> talks about the <code>&lt;header&gt;</code> as</p>
<blockquote><p>The header element represents introductory content for its nearest ancestor sectioning content or sectioning root element. A header typically contains a group of introductory or navigational aids.</p></blockquote>
<p>And goes on to note</p>
<blockquote><p>A header element is intended to usually contain the section’s heading (an h1–h6 element), but this is not required. The header element can also be used to wrap a section’s table of contents, a search form, or any relevant logos.</p></blockquote>
<p>So what these are saying is that whichever section we are in we can use <code>&lt;header&gt;</code> to denote any introductory content. As their note says, normally this is the heading, but it could really be anything you need to be introductory.</p>
<p>The upshot of this is that perhaps we could be marking up things like tldr; and short introductions better. I can certainly see a case where assistive technologies might decide to deprioritise content held within there in favour of the meat of the article.</p>
<p>Unfortunately at the moment if you are a WordPress user like me your hands are pretty tied as this isn’t something offered out of the box or by any plugins I have found, but certainly something to consider if you have full control over your content.</p>
