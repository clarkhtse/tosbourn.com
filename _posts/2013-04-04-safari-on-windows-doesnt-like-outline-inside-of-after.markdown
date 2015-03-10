---
layout: post
status: publish
published: true
title: Safari on Windows doesn't like outline inside of :after
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1422
wordpress_url: http://tosbourn.com/?p=1422
date: '2013-04-04 19:22:47 +0100'
date_gmt: '2013-04-04 18:22:47 +0100'
categories:
- Development Help
tags:
- CSS
- Internet Explorer 8
- Safari
- Windows
- Chris Smith
comments: []
---
<p>Here is a really strange edgecase of browser support for you, Safari on Windows doesn't like <code>outline</code> when it is called inside the <code>:after</code> psudoselector.</p>
<p>The first thing to note is that Apple have stopped supporting the Safari browser on Windows (I learned this today from Chris at ExamTime) so this probably isn't something that is going to be high on your to-fix list even if this did crop up in production. I am simply blogging about it because I couldn't find reference to it anywhere on the net and was starting to think I was imagining things.</p>
<p>So this is how the issue breaks down.</p>
<ul>
<li>Safari (assume I mean on Windows unless I say otherwise) supports :after</li>
<li>Safari supports outline</li>
<li>Safari does not support outline when called inside :after</li>
<li>Safari does support border when called inside :after (which basically does the same thing)</li>
<li>Internet Explorer 8 does not support border when called inside :after (but does support outline)</li>
</ul>
<p>This makes little sense to me, I have heard of browsers not supporting certain properties and certain selectors, but not a combination. Here is some code you can use to verify;</p>
<pre><code>
&lt;html&gt;
 &lt;head&gt;
  &lt;style&gt;
   .test:after { outline: green solid 1px; position:absolute; top:0; bottom:0; left: 50%}
  &lt;/style&gt;
 &lt;head&gt;
 &lt;body&gt;
  &lt;div class="test"&gt;&lt;/div&gt;
&lt;/html&gt;
</code></pre>
<p>Mental.</p>
