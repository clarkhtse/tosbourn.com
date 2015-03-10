---
layout: post
status: publish
published: true
title: Too many posts about the same thing on your Twitter timeline?
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 787
wordpress_url: http://tosbourn.com/?p=787
date: '2012-01-06 10:35:40 +0000'
date_gmt: '2012-01-06 09:35:40 +0000'
categories:
- Other
tags:
- Twitter
- jQuery
comments: []
---
<p>I was getting annoyed about the amount of posts about one particular topic on my timeline this morning and I decided I could fix the issue with some jQuery.</p>
<p><code><br />
var term = $('.twitter-anywhere-tweet-box-editor').val();<br />
$(".stream-item:contains('" + term + "')").css('display','none');<br />
</code></p>
<p>If you save it as a bookmarklet you can use this by typing the term you want to disappear from your timeline in the search box and then clicking the bookmarklet.</p>
<p><code>javascript:var term = $('.twitter-anywhere-tweet-box-editor').val();$(".stream-item:contains('" + term + "')").css('display','none');</code></p>
<p>That has no practical application really as it doesn't persist over page reloads and only lets you do one phrase at a time, but it helped me vent some frustration at dumb tweets!</p>
