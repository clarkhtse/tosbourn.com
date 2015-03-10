---
layout: post
status: publish
published: true
title: Please stop using features by testing for browser
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2364
wordpress_url: http://tosbourn.com/?p=2364
date: '2014-10-27 10:18:45 +0000'
date_gmt: '2014-10-27 09:18:45 +0000'
categories:
- Development Help
tags: []
comments: []
---
<p>Today I had to debug some code that up until fairly recently was working 100%.</p>
<p>The issue was the code (some jQuery) was checking to see if the browser was Firefox and if it was it should use some Firefox specific code;</p>
<pre><code>if ($.browser.mozilla) { e.mozSlice(a,b) }</code></pre>
<p>Up until version 30 of Firefox this code would have worked, but <code>mozSlice</code> hasn't been needed for some time and was finally removed as of Firefox 30.</p>
<p>Now, there are a few ways around this, a really naive way would be to add in some version checking as well, so if the browser is Firefox and the version is &lt; 30 use <code>mozSlice</code>, else use slice.</p>
<p>These type of checks are really redundant and in 6 months time you will revisit the code and wonder what was so special about version 30, instead you can make your code much more clear by testing instead for the feature itself.</p>
<pre><code>if (undefined !== e.mozSlice) { e.mozSlice(a, b) }</code></pre>
<p>This code says, if we have access to mozSlice, lets use it.</p>
<p>This means that first of all if Internet Explorer decided to implement the <code>mozSlice</code> function instead of Slice this would work, it also means that if Firefox decided to drop <code>mozSlice</code> (which they have) nothing would break.</p>
