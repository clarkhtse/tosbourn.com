---
layout: post
status: publish
published: true
title: Hearthstone APIs
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2561
wordpress_url: http://tosbourn.com/?p=2561
date: '2015-02-15 12:47:09 +0000'
date_gmt: '2015-02-15 11:47:09 +0000'
categories:
- Development Help
tags:
- API
- '365'
- Hearthstone
comments:
- id: 698
  author: james young
  author_email: jmeyoung@gmail.com
  author_url: http://jamsyoung.com/
  date: '2015-03-01 17:03:00 +0000'
  date_gmt: '2015-03-01 16:03:00 +0000'
  content: |-
    Here is a Hearthstone RESTful API that I created as a side project.  It is updated as of 2.2.0.8036.

    I threw it up on 3scale. Feel free to check it out.

    https://jamsyoung.3scale.net
    https://github.com/jamsyoung/hearthstone-api
- id: 699
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-03-01 17:11:00 +0000'
  date_gmt: '2015-03-01 16:11:00 +0000'
  content: Oh nice! Thanks :-)
---
<p>I love playing Hearthstone, and I love developing stuff. It seemed like a natural fit for me to want to develop something on top of Hearthstone.</p>
<p>This post is just some notes I have taken while researching Hearthstone APIs.</p>
<h2>Hearthstone?</h2>
<p>Hearthstone is a free to play online card game where you try and beat your opponent by playing cards that counteract their cards and gain board advantage. If you have ever played Magic the Gathering or even the Pokemon card games it is in the same area.</p>
<p>It is fun and while you can easily spend hours in the game the individual games only last 10 or so minutes, so you can get quick Hearthstone fixes!</p>
<h2>The data I would love</h2>
<p>In an ideal world the data that would be exposed is;</p>
<ul>
<li>Card info</li>
<li>Match info</li>
<li>Player stats</li>
<li>Deck info</li>
</ul>
<p>Each of these come with their own set of questions around what would players want, and some would be far harder to achieve than others. Like I say, an in an ideal world!</p>
<h2>Official Hearthstone API</h2>
<p>Unfortunately there isn't one, and I can't find any source from Blizzard that would suggest there is going to be on at any point in the future.</p>
<p>This means I am going to need to look at unofficial, fan-made APIs.</p>
<h2>Lots of Dead Ends</h2>
<p>Before I talk about the couple of APIs that I did manage to find. I must warn you that there are currently a lot of dead ends. A lot of old conversations that end in links which go nowhere.</p>
<p>Notable examples are hearthstone-api.com and hearthstoneapi.com – both of which promised so much but didn't stand the test of time!</p>
<h2>Hearthstone JSON</h2>
<p>The first result many people will come across is <a href="http://hearthstonejson.com">Hearthstone JSON</a>, this is a great project which provides a JSON file that you can feed into your application to query card information.</p>
<p>It is updated regularly. At the time of writing this post Hearthsone JSON has been updated to reflect the Hearthstone changes as per patch 2.1.0.7628, which I believe are the newest changes currently available.</p>
<p>The JSON is generated using <a href="https://github.com/Sembiance/hearthstonejson">a tool</a> which grabs the data straight from Hearthstone game files.</p>
<p>The only issue I can see with this is that you would want the JSON stored locally in your project, so you would need to either write something to attempt to see when the JSON file is updated or you would need to manually remember to look for updates. Thinking about it I guess you could just grab the latest JSON blindly every so often – I wouldn't want to put too much load on their server though if everyone was doing that.</p>
<h2>IrythiaHS</h2>
<p><a href="https://www.mashape.com/irythia/hearthstone">IrythiaHS</a> tries to solve the problem of keeping your data up to date by being a third party API which you can actively query. This means no local JSON files and when it gets updated all clients talking to it would be updated.</p>
<p>The API is hosted by MashApe which is a service which manages APIs for folk, I signed up (free) and it seems useful.</p>
<p>My main concern with Irythia is that the data didn't seem to be kept up to date. For example Madder Bomber wasn't found in its list of single cards.</p>
<p>This would make me unlikely to want to use it.</p>
<h2>Room for improvement?</h2>
<p>Unless Hearthstone comes out with an official API I don't think we will get many of the things on my wishlist, so focusing purely on card details I think if the two APIs I have found were to be combined that would be ideal.</p>
<p>I am tempted to make something on top of Hearthstone JSON that would make this possible.</p>
<h2>What have I missed?</h2>
<p>If you know of other APIs either completed or in the works that I should mention in this post, please let me know in the comments.</p>
