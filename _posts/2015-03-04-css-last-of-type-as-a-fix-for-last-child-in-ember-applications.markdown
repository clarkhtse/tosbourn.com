---
layout: post
status: publish
published: true
title: CSS last-of-type as a fix for last-child in Ember applications
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2627
wordpress_url: http://tosbourn.com/?p=2627
date: '2015-03-04 11:47:02 +0000'
date_gmt: '2015-03-04 10:47:02 +0000'
categories:
- Development Help
tags:
- CSS
- Ember
- last-of-type
- last-child
comments: []
---
<p>Today I was scratching my head wondering why a basic <code>last-child</code> selector wasn't working on a page I was styling up.</p>
<p>A quick look at the DOM reminded me that Ember likes to litter the DOM with <code>&lt;script&gt;</code> tags.</p>
<p>So instead of having a nice list like;</p>
<pre><code>&lt;ul&gt;
  &lt;li&gt;One&lt;/li&gt;
  &lt;li&gt;Two&lt;/li&gt;
&lt;/ul&gt;
</code></pre>
<p>We get something similar to</p>
<pre><code>&lt;ul&gt;
  &lt;li&gt;One&lt;/li&gt;
  &lt;script id="metamorph-1-start" type="text/x-placeholder"&gt;&lt;/script&gt;
  &lt;script id="metamorph-1-end" type="text/x-placeholder"&gt;&lt;/script&gt;
  &lt;li&gt;Two&lt;/li&gt;
  &lt;script id="metamorph-2-start" type="text/x-placeholder"&gt;&lt;/script&gt;
  &lt;script id="metamorph-2-end" type="text/x-placeholder"&gt;&lt;/script&gt;
&lt;/ul&gt;
</code></pre>
<p>When we use <code>last-child</code> in CSS it is normally on a repeating collection of things so we don't really think about the elements around them. In the example above however <code>&lt;li&gt;Two&lt;/li&gt;</code> is not the <code>last-child</code> of anything, that last <code>&lt;script&gt;</code> tag is.</p>
<h2>In comes last-of-type</h2>
<p>Luckily there is a way around this with the <code>last-of-type</code> selector in CSS. This works exactly the same as <code>last-child</code> only it takes the type of the elements into consideration.</p>
<p>This means the following CSS will now work as expected;</p>
<pre><code>ul li::after { content: ", "}
ul li:last-of-type::after { content: ""}
</code></pre>
<h2>Not just Ember</h2>
<p>Whilst this is the first time I have had to think about things like this, I think I will be using this method from now on – it is more strict and acts exactly how I want it to act. With front end web development at the moment there could be several things making changes to the DOM on the fly and potentially knocking out things like <code>last-child</code></p>
