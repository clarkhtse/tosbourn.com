---
layout: post
status: publish
published: true
title: Disqus showing bullets.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 487
wordpress_url: http://tosbourn.com/?p=487
date: '2011-07-29 13:25:15 +0100'
date_gmt: '2011-07-29 12:25:15 +0100'
categories:
- Development Help
tags:
- CSS
- Disqus
comments:
- id: 41
  author: Mistersimard
  author_email: mistersimard@gmail.com
  author_url: ''
  date: '2011-08-27 07:11:00 +0100'
  date_gmt: '2011-08-27 06:11:00 +0100'
  content: 'Dude, I actually wanna give you money for this! I googled "bullets showing
    up in disqus", found this and it worked! Just goes to show that it''s always worth
    posting little solutions like this online, because SOMEONE is always going to
    run into it as well. '
- id: 42
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-08-27 11:30:00 +0100'
  date_gmt: '2011-08-27 10:30:00 +0100'
  content: Glad it could be of service!
- id: 66
  author: Matt
  author_email: funcfish@gmail.com
  author_url: http://funcfish.com
  date: '2011-11-08 03:41:00 +0000'
  date_gmt: '2011-11-08 02:41:00 +0000'
  content: |-
    Toby, thanks for posting this.  It also was the first thing I saw on Google.  

    In my situation there was a background image that my theme was throwing on the top commenters widget.  I had to add some CSS to get rid of my theme's styling and then I was cool.  Here is the CSS I had to use in case someone else has trouble.

    .suf-widget li {  background-image: none;}
- id: 67
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-11-08 09:40:00 +0000'
  date_gmt: '2011-11-08 08:40:00 +0000'
  content: Thanks for sharing it, hopefully it saves someone else some time!
- id: 83
  author: Jennifer Allen
  author_email: md@bestsexpositions.com
  author_url: http://bestsexpositions.com/
  date: '2011-12-02 20:48:00 +0000'
  date_gmt: '2011-12-02 19:48:00 +0000'
  content: That seems llike the logical fix, but sadly when I tried it, it didn't
    work :(
- id: 84
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-12-02 21:03:00 +0000'
  date_gmt: '2011-12-02 20:03:00 +0000'
  content: Send me the link to your site and I could take a quick look if you like.
- id: 85
  author: Jennifer Allen
  author_email: md@bestsexpositions.com
  author_url: http://bestsexpositions.com/
  date: '2011-12-05 08:18:00 +0000'
  date_gmt: '2011-12-05 07:18:00 +0000'
  content: I figured out a workaround by removing the ul style for contentleft from
    my css. Thanks for having me look at dsq overrides, though. B)
- id: 86
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-12-05 08:25:00 +0000'
  date_gmt: '2011-12-05 07:25:00 +0000'
  content: No bother, glad you got there in the end!
- id: 87
  author: erica
  author_email: erica@iheartcvs.com
  author_url: http://iheartcvs.com
  date: '2011-12-08 01:48:00 +0000'
  date_gmt: '2011-12-08 00:48:00 +0000'
  content: thanks so much!
- id: 88
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2011-12-08 07:51:00 +0000'
  date_gmt: '2011-12-08 06:51:00 +0000'
  content: Glad it helped!
- id: 112
  author: Record Recorder
  author_email: joparac@gmail.com
  author_url: http://www.recordrecorder.com/
  date: '2012-02-11 04:07:00 +0000'
  date_gmt: '2012-02-11 03:07:00 +0000'
  content: gotta love disqus - thanks 
- id: 302
  author: I &lt;3 Self-Cut Systems
  author_email: jrwriter@diplomats.com
  author_url: ''
  date: '2013-12-11 09:46:00 +0000'
  date_gmt: '2013-12-11 08:46:00 +0000'
  content: |-
    #disqus_thread ul {
        list-style: none outside none;
    }
---
<p>I finally got around to fixing the stupid looking bullets that appeared on a lot of the parts of the disqus commenting system.</p>
<p>The issue, of course, was that my stylesheet wasn't designed to hide the style of the unordered list items.  Here is the code I needed to add to remove the bullets.</p>
<pre>#disqus_thread ul {
    list-style: none outside none;
}</pre>
<p>Hope it helps someone.</p>
