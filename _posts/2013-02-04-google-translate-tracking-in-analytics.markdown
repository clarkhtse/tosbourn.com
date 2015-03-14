---
layout: post
status: publish
published: true
title: Google Translate tracking in Analytics
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1292
wordpress_url: http://tosbourn.com/?p=1292
date: '2013-02-04 14:53:51 +0000'
date_gmt: '2013-02-04 13:53:51 +0000'
categories:
- Other
tags:
- Google Analytics
- Google Translate
comments:
- id: 386
  author: Kaman
  author_email: kamancheung@gmail.com
  author_url: ''
  date: '2014-01-23 04:37:00 +0000'
  date_gmt: '2014-01-23 03:37:00 +0000'
  content: I've been looking for this everywhere!  Thanks for sharing
- id: 387
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-23 11:23:00 +0000'
  date_gmt: '2014-01-23 10:23:00 +0000'
  content: Glad it helped! :-)
- id: 468
  author: Srihari K
  author_email: karanthsrihari@gmail.com
  author_url: http://trackmyphones.com
  date: '2014-05-11 06:00:00 +0100'
  date_gmt: '2014-05-11 05:00:00 +0100'
  content: This doesnt seem to be valid for new analytics UI. Any idea where i can
    find that report in the new UI?
- id: 469
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-05-11 14:17:00 +0100'
  date_gmt: '2014-05-11 13:17:00 +0100'
  content: 'Good point, I have updated it: Behaviour &gt; Events &gt; Overview &gt;
    Google Website Translator'
- id: 470
  author: Guest
  author_email: anonymized-1379712709@disqus.com
  author_url: ''
  date: '2014-05-11 17:31:00 +0100'
  date_gmt: '2014-05-11 16:31:00 +0100'
  content: Brilliant! Its working! didnt find this even in analytic forum! Thanks.
- id: 471
  author: Srihari K
  author_email: karanthsrihari@gmail.com
  author_url: http://trackmyphones.com
  date: '2014-05-11 17:31:00 +0100'
  date_gmt: '2014-05-11 16:31:00 +0100'
  content: Brilliant! Its working! did'nt find this even in analytic forum! Thanks
- id: 480
  author: nitty83
  author_email: henric.folke@gmail.com
  author_url: ''
  date: '2014-05-15 15:49:00 +0100'
  date_gmt: '2014-05-15 14:49:00 +0100'
  content: Hi guys. I need some help with this. I've implemented the meta tag and
    the snippet on my site after adding my analytics id in settings. But when changing
    language on the site it doesn't trigger any events. I see the page view but no
    events. What am I doing wrong?
- id: 483
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-05-17 22:06:00 +0100'
  date_gmt: '2014-05-17 21:06:00 +0100'
  content: |-
    Hi Nitty!

    I am not sure what it could be, the best thing for you to do would be to put a sample of your code onto something like webmasters.stackexchange.com and ask for help there, once we see your code we could probably easily work it out :-)
- id: 491
  author: jegs1
  author_email: jegs1@jegsworks.com
  author_url: ''
  date: '2014-05-31 23:36:00 +0100'
  date_gmt: '2014-05-31 22:36:00 +0100'
  content: Thanks Toby for the bread crumbs to the treasure, ie report on translator
    events. I just implemented the analytics code after having the translator widget
    on my pages for quite a while. That widget seems to slow the page loading so now
    I can find out if it is being used at all!
---
<p>Recently I decided to set up Google Translate on my <a href="http://thefootytipster.com">football tips</a> website.</p>
<p>tl;dr; To find this information in Google Analytics go to <b>Behaviour &gt; Events &gt; Overview &gt; Google Website Translator</b></p>
<p>During the setup process Google Translate asked me if I wanted to record translations inside of Google Analytics, I selected yes and gave them my UA code to enable this — I figured getting good analytics of how this is being used would let me know if a) it is worth having and b) what languages are being made use.</p>
<p>After letting it run for a few days I thought I would jump into Google Analytics and take a look how things were shaping up, I couldn't immediately find anything to do with Translate inside of Analytics so I decided to do some searching.</p>
<p>My first lot of searches just returned people asking the question about where to look for this information inside of Analytics and having a go at Google for not making this easy.</p>
<p>I decided I would take a more thorough look through Analytics figuring it must be somewhere, and sure enough hiding inside of Events I found it.</p>
<p>In retrospect Events makes a lot of sense to house someone translating something on your website but considering the amount of sub-sections that Google Analytics has that could be interpreted as an event you can forgive anyone for not finding it immediately.</p>
<p>To to reiterate my tl;dr; above, if you log into your Analytics and go to <b>Content</b>, then <b>Events</b>, then <b>Overview</b> you will see all of your Events, Google Translate will be one of those events.</p>
<p>To get a good breakdown by language used you should open up the Google Translate report and select as your secondary dimension <b>Event Label</b>, you will then see something like this;</p>
<p>&nbsp;</p>
<p><img class="size-full wp-image-1293" src="http://tosbourn.com/wp-content/uploads/2013/02/Screen-Shot-2013-02-04-at-13.44.16.png" alt="Google Analytics Report of Translated Items" width="797" height="368" /> Google Analytics Report of Translated Items</p>
