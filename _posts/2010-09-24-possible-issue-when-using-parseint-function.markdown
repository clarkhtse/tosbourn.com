---
layout: post
status: publish
published: true
title: Possible issue when using parseInt function.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 319
wordpress_url: http://www.tosbourn.com/?p=319
date: '2010-09-24 10:05:39 +0100'
date_gmt: '2010-09-24 09:05:39 +0100'
categories:
- Development Help
tags:
- JavaScript
- parseInt
comments: []
---
<p>@<a href="http://twitter.com/psynnott" target="_blank">psynnott</a> recently pointed out that there was a potential issue in some of the code we had written.  It involved using the <strong>parseInt</strong> function of JavaScript in order to ensure we are dealing with integer values.</p>
<p>He noticed that if you pass a string of '09' the function will attempt to treat the value as an octal (which is a fairly insane thing to have as a default in my opinion) in order to fix this you would change</p>
<p><code>var test = parseInt('09');</code></p>
<p>to</p>
<p><code>var test = parseInt('09',10);</code></p>
<p>This will force base 10 to be used instead of octal.</p>
