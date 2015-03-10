---
layout: post
status: publish
published: true
title: Passing a day of the week into Ruby's Date.parse
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1588
wordpress_url: http://tosbourn.com/?p=1588
date: '2013-07-10 14:58:47 +0100'
date_gmt: '2013-07-10 13:58:47 +0100'
categories:
- Development Help
tags:
- Ruby
- Date
comments:
- id: 177
  author: mog
  author_email: disqus.com@mog.se
  author_url: ''
  date: '2013-07-10 15:12:00 +0100'
  date_gmt: '2013-07-10 14:12:00 +0100'
  content: Date.current.beginning_of_week if you have ActiveSupport, which is pretty
    standard.
- id: 178
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-07-10 15:18:00 +0100'
  date_gmt: '2013-07-10 14:18:00 +0100'
  content: |-
    Cheers @mog:disqus - of course you are right, but with what I was doing I didn't want to jump into anything else.

    I also noticed when testing that `beginning_of_week` for me was set to be a Monday, I am sure this is something I can change but I quite like telling Ruby exactly when I want my date to be.
- id: 179
  author: max
  author_email: what@ever.com
  author_url: ''
  date: '2013-07-10 18:30:00 +0100'
  date_gmt: '2013-07-10 17:30:00 +0100'
  content: be careful with Date.parse - it is quite slow. for instance when you have
    a string with date in some(known) format - it's lightyears faster to regexp the
    crap out of it than to use Date.parse
- id: 180
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-07-10 19:37:00 +0100'
  date_gmt: '2013-07-10 18:37:00 +0100'
  content: Cheers for the heads up @23c0c588fc16ff876a6c6e30529ed37d:disqus  - I hadn't
    benchmarked it at all.
- id: 486
  author: Luke Griffiths
  author_email: wlgriffiths@gmail.com
  author_url: ''
  date: '2014-05-21 17:39:00 +0100'
  date_gmt: '2014-05-21 16:39:00 +0100'
  content: Good to know Toby!  Just wanted to add that in order to use this method
    from a straight irb session (not a rails console), you need to `require 'date'`
    which loads the standard implementation.  Kinda counter-intuitive.  Thanks to
    http://stackoverflow.com/a/12544638/431211
---
<p>Did you know you can pass a day of the week into Ruby's Date.parse function? For example you could do something like this;</p>
<pre><code>friday = Date.parse('Friday')
p friday =&gt; #&lt;Date: 2013-07-12 ((2456486j,0s,0n),+0s,2299161j)&gt;</code></pre>
<p>This is pretty useful, it seems to return the date closest to the day you enter, and of course this will be based on your server's date and time settings.</p>
<p>If you wanted to work out the date at the start of the current week and your week starts on Sunday, you could do something like;</p>
<pre><code>sunday = Date.parse('Sunday')
if sunday &gt; Date.today
    sunday -= 7
end</code></pre>
<p>This is a super quick way of playing with dates without needing to rely on any gems.</p>
