---
layout: post
status: publish
published: true
title: PHP - Quick Is Not Set Replace
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 286
wordpress_url: http://www.tosbourn.com/?p=286
date: '2010-09-01 14:35:15 +0100'
date_gmt: '2010-09-01 13:35:15 +0100'
categories:
- Development Help
tags:
- PHP
- isset
- code
comments: []
---
<p>During a recent PHP update I started getting a load of warnings in my code regarding undefined variables, whatever point release I was on must have been a little more relaxed about it than the newer version.</p>
<p>Some of the time it was obvious that it was bad coding on my part, some variables really did need to be assigned when I was just assuming they were going to be assigned due to the flow of the code.  Other times however I was left having to use <em><strong>isset()</strong></em> to see if a variable was set and if not act accordingly.</p>
<p>90% of the time acting accordingly meant set it to some value (usually NULL, 0 or '').  In order to keep my code nice and tidy I took 5 minutes to write a quick function to help, I leave it here on the chance it may be of some use to someone else as well.</p>
<pre><code>
/*
* This will either return itself or a passed in alternative
* depending on if the passed in variable is set or not.
*/
function issetOr(&amp;$first, $alternative = NULL) 
{
    $output = '';
    if (isset($first)) {
        $output = $first;
    } else {
        $output = $alternative;
    }
    return $output;
}
</code></pre>
