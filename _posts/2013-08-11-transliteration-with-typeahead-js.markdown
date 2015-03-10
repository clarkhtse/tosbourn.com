---
layout: post
status: publish
published: true
title: Transliteration with Typeahead.js
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1616
wordpress_url: http://tosbourn.com/?p=1616
date: '2013-08-11 16:39:25 +0100'
date_gmt: '2013-08-11 15:39:25 +0100'
categories:
- Development Help
tags:
- JavaScript
- Typeahead.js
- Transliteration
comments: []
---
<p>Often in real world web applications we have to deal with words or characters that fall outside of the standard latin-based keyboard character set.</p>
<p>For example lets say we wanted our users to search through a list of torrent clients, a list wouldn't be complete without including µTorrent, but here we have two problems.</p>
<ol>
<li>Very few people will know how to type µ or have the inclination to look it up.</li>
<li>If they just type torrent, we presume that most torrent clients will have torrent in their name, so this isn't going to narrow down the search too much.</li>
</ol>
<p>The solution is to use tokens in our datum, so where as before we might have just had;</p>
<pre><code>{"value": "µTorrent"}</code></pre>
<p>We would now have;</p>
<pre><code>{
  "value" : "µTorrent",
  "tokens": ["µTorrent", "uTorrent"]
}</code></pre>
<p>Which means if our user types in 'u', typeahead.js will know to return µTorrent amongst the results.</p>
<p>I hope this post has helped someone, did you know I have written a <a title="Typeahead.js The Book!" href="http://tosbourn.com/2013/08/javascript/typeahead-js-the-book/">book on Typeahead</a>?</p>
