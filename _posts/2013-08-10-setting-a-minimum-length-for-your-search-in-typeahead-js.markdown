---
layout: post
status: publish
published: true
title: Setting a minimum length for your search in Typeahead.js
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1611
wordpress_url: http://tosbourn.com/?p=1611
date: '2013-08-10 15:50:10 +0100'
date_gmt: '2013-08-10 14:50:10 +0100'
categories:
- Development Help
tags:
- Jasmine
- Typeahead.js
comments:
- id: 303
  author: Adan
  author_email: holler@adanaltamira.com
  author_url: ''
  date: '2013-12-11 21:41:00 +0000'
  date_gmt: '2013-12-11 20:41:00 +0000'
  content: Thank you.
---
<p>I was looking through the Jasmine tests for Typeahead.js whilst doing research for a book I am writing on the subject and I noticed a handy little thing that isn't documented on the Github page.</p>
<p>You can pass in <code>minLength</code> with your dataset and this means no lookups will be completed until the user has entered in enough characters, for example;</p>
<pre><code>$('#people').typeahead({
  name: 'people',
  prefetch: './names.json',
  minLength: 3
});</code></pre>
<p>This helps to greatly reduce the amount of lookups your code will do and will be helpful when you know that the first couple of characters the user enters is going to bring back too many results to be useful.</p>
<p>Obviously you don't want to set this value to be greater than the length of your smallest possible return value, and if you make it too large the user might not know that there is a typeahead feature enabled.</p>
<p>I hope this helped, if you want to learn more about <a title="Typeahead.js The Book!" href="http://tosbourn.com/2013/08/javascript/typeahead-js-the-book/">Typeahead.js I have written a book on it</a>!</p>
