---
layout: post
status: publish
published: true
title: Parameterise everything.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 624
wordpress_url: http://tosbourn.com/?p=624
date: '2011-10-18 13:08:43 +0100'
date_gmt: '2011-10-18 12:08:43 +0100'
categories:
- Other
tags:
- Rant
- Best Practice
comments: []
---
<p>Programming 101 tells us that hard coding values into programs is bad.  So bad, in fact, that you will lose marks when you hard code values in your solutions.  Pick up any beginner programming textbook and the very first chapter will almost certainly be about variables and it will no doubt tell you how wonderful they are because it stops hard coding.</p>
<p>That being the case why on earth are developers out there still hard coding stuff? Like stupidly large amounts of stuff.  There are three possible reasons in my opinion for wanting to hard code something.</p>
<ol>
<li>You don't know any better.</li>
<li>You think you are saving time.</li>
<li>You want people to come to you for changes.</li>
</ol>
<p>Let me answer these in turn;</p>
<ol>
<li>If you don't know any better you need to go back to school or back to the drawing board, this is basic stuff and if you don't know this there are some serious gaps in your knowledge.</li>
<li>This is probably the most common excuse, the fact is though, you are not saving time, you are maybe saving a little bit of time in the short term but when you come to update your code at some point in the future, that time will be lost digging around and wondering why changing something on line 5 doesn't effect a calculation on line 50.</li>
<li>If you are trying to get some sort of job security by forcing people to come to come to development for changes then you are not only a terrible person, but a complete blight on our industry.  You should focus on job security by crafting creative solutions to unsolved problems, not ripping people off.</li>
</ol>
<p>Now when I say things should be parameterised, I don't mean you need to create a front end for your end user to edit absolutely everything, this could actually be quite dangerous and it certainly wouldn't be a nice user experience but in the code you create everything should be in either a variable and a constant - and these need to be given useful, intuitive names and if it isn't blindingly obvious what the variable or constant is doing you need to take the 3 seconds it takes to put a comment in and comment it.</p>
<p>If you are a customer who has paid for some development company to create you something, and they charge more than 30 minutes for making one text change, ask them why it takes so long - you should be demanding more out of your company because, frankly there are some jokers out there and they need to be called out on it.</p>
