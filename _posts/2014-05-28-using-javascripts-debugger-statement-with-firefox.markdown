---
layout: post
status: publish
published: true
title: Using JavaScript's debugger statement with Firefox
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1916
wordpress_url: http://tosbourn.com/?p=1916
date: '2014-05-28 11:09:28 +0100'
date_gmt: '2014-05-28 10:09:28 +0100'
categories:
- Development Help
tags:
- Firefox
- JavaScript
- Debugging
- Venkman
comments: []
---
<p>If you don't use the <code>debugger</code> statement in JavaScript you are either very fortunate or you are missing a massive trick. You stick the statement <code>debugger;</code> in your JavaScript file and when JavaScript execution gets to it so long as you have your console open everything will pause and you can poke around the code live by calling things from the context you placed the debugger in. Super powerful.</p>
<p>Whilst Chrome supports this feature out of the box in Firefox this doesn't seem to be the case.</p>
<p>Happily there is a super easy fix, install the <a href="https://addons.mozilla.org/en-US/firefox/addon/javascript-debugger/">Venkman JavaScript Debugger Plugin</a> and you can debug as you would in Chrome.</p>
<p>I noticed this while reading an MDN article on <a href="https://developer.mozilla.org/en/docs/Debugging_JavaScript#Call_stack">debugging JavaScript</a>.</p>
<p>For more information on general debugging JavaScript with Firefox there is a great article over on <a href="https://developer.mozilla.org/en-US/docs/Tools/Debugger">MDN</a>.</p>
