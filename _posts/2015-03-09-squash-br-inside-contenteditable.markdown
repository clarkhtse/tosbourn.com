---
layout: post
status: publish
published: true
title: Squash br inside contenteditable
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2646
wordpress_url: http://tosbourn.com/?p=2646
date: '2015-03-09 15:49:15 +0000'
date_gmt: '2015-03-09 14:49:15 +0000'
categories:
- Development Help
tags:
- CSS
- '365'
- contenteditable
comments: []
---
<p>This has to go down as one of my favourite little CSS hacks of late.</p>
<p>I am not a big fan of <code>contenteditable</code>. I think it has a use but it is too easy to misuse and we end up using it for things that <code>input type='text'</code> was really meant for.</p>
<p>One thing that <code>contenteditable</code> does by default which isn't ideal in most situations is that it allows a carriage return to create a <code>&lt;br /&gt;</code> inside the element marked as <code>contenteditable</code>.</p>
<p>Now you are smart people so you are only grabbing the text from inside the <code>contenteditable</code> element when it comes to saving that data somewhere, so the <code>&lt;br /&gt;</code> won't persist. Still until the page/data refresh it looks pretty ugly.</p>
<h2>Enter CSS</h2>
<p>This is such a simple hack, which I think is why I love it;</p>
<p>HTML</p>
<pre><code>&lt;div class="div_that_thinks_it_is_input" contenteditable="true"&gt;&lt;/div&gt;
</code></pre>
<p>CSS</p>
<pre><code>.div_that_thinks_it_is_input br { display: none }
</code></pre>
<p>We just don't display the <code>&lt;br /&gt;</code>, no need to get JavaScript to try and parse it out, no need to listen to keyPresses to try and stop it from ever appearing.</p>
<p>If you want a more generalised form of this you can always do;</p>
<pre><code>[contenteditable="true"] br { display: none }
</code></pre>
