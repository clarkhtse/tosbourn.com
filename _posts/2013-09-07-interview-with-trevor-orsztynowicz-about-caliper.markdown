---
layout: post
status: publish
published: true
title: Interview with Trevor Orsztynowicz about Caliper
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1658
wordpress_url: http://tosbourn.com/?p=1658
date: '2013-09-07 22:49:49 +0100'
date_gmt: '2013-09-07 21:49:49 +0100'
categories:
- Interviews
tags:
- JavaScript
- Sublime Text 2
- Interview
- Trevor Orsztynowicz
- Calper
- Vim
comments:
- id: 620
  author: Randy Browning
  author_email: randyfromsono@gmail.com
  author_url: ''
  date: '2014-09-29 02:21:00 +0100'
  date_gmt: '2014-09-29 01:21:00 +0100'
  content: "This is a person that has stated that he takes pride in being a 'Hacker',
    is well known has recently been involved in blatant plagiarism. \nIt's possible
    that he believes that as a person in Canada he can continue with this type of
    activity with impunity."
- id: 621
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-09-29 09:25:00 +0100'
  date_gmt: '2014-09-29 08:25:00 +0100'
  content: |-
    Hey Randy - I know nothing of this plagiarism, but when we use the word hacker it differs wildly from when the media does.

    http://en.wikipedia.org/wiki/Hacker_(programmer_subculture)

    I don't understand why the Canadian thing makes a difference in your comment, you almost sound like America controls the web?
- id: 623
  author: Randy Browning
  author_email: randyfromsono@gmail.com
  author_url: ''
  date: '2014-09-29 19:28:00 +0100'
  date_gmt: '2014-09-29 18:28:00 +0100'
  content: "Hacker is the term that this person used himself as a description in his
    occupation. I'm sure there are many interpretations and definitions. (And when
    you say, 'the media',  who or what are you referring to?)\nI don't want to get
    into a debate as to who controls the web since it' not even relevant. The Canadian
    'thing' may NOT make any difference. When there is a legal dispute,  it IS more
    likely to be settled if the adversaries live in the same country.  \nPlagiarism,
    by the way,  means copying without permission.  \nI should also add, that I don't
    have the slightest interest, or inclination to bring these subjects up.  I just
    want to allow this person to correct a bad decision he has made.  That's what
    this about.  Not who controls the web etc. I'm thinking (hoping) he will."
---
<p><a href="http://tosbourn.com/wp-content/uploads/2013/09/logotype_dark_48.png"><img class="alignright size-full wp-image-1660" src="http://tosbourn.com/wp-content/uploads/2013/09/logotype_dark_48.png" alt="logotype_dark_48" width="211" height="48" /></a>Today I am talking with Trevor Orsztynowicz about his exciting new company <a href="http://caliper.io/">Caliper.io</a>.</p>
<p>Caliper is performance monitoring for single page webapps by hooking into tools like Ember.js</p>
<p>I want to thank Trevor for taking the time to answer my questions, and would urge you all to check out the site, now, onto the interview!</p>
<p><strong>Could you tell us a little more about yourself, a bit about your personal history?</strong></p>
<p><a href="http://tosbourn.com/wp-content/uploads/2013/09/trevor_DSC8640-3.jpg"><img class="alignright size-thumbnail wp-image-1661" src="http://tosbourn.com/wp-content/uploads/2013/09/trevor_DSC8640-3-150x150.jpg" alt="trevor_DSC8640-3" width="150" height="150" /></a>Sure! I started programming when I was a kid. My Dad had an Amiga 2000 and I really wanted to figure out how to make those demoscene hacks. That involved getting on BBSes - I'm sort of showing my age - and reading a lot of books that went way over my head.</p>
<p>Eventually my dad bought a PC and brought home a magazine with a penguin on it and I became obsessed with all the infrastructure the powered the internet. That led to a background in telecommunications, and systems administration.</p>
<p>That's how I started my first company, which was a cloud computing startup called Layerboom. We built a distributed infrastructure management platform based on KVM. All you had to do was network boot your servers off our software and it built you a mini EC2. Literally took 10 minutes. I sold that company to Joyent - the guys behind SmartOS and Node.</p>
<p><strong>I can’t say anything as my first computer experiences where Amiga based! Can you tell us a little bit about your company Caliper, what it is and what made you want to found the company?</strong></p>
<p>Caliper is a monitoring service with a twist. Instead of monitoring your server and inferring client experience, we just measure the experience on the client directly.</p>
<p>We'd been following a trend in the development community which was the shift to single page applications. The browser has basically turned from a pretty document viewer into the worlds largest application runtime environment. That shift also includes moving to APIs for storing all your data. All those things represent a massive refactoring of the web, and we realized the best way to measure a user's experience would be to do it on their client directly.</p>
<p><strong>There are currently three of you working on the project, may I ask how you all came together?</strong></p>
<p>I met Kalv a year ago after leaving my last job to take a break. My break didn't last very long - we started working on a few projects together which were pretty interesting.</p>
<p>We ended up working on a project for a client and that's how we stumbled into the single page app space.</p>
<p>Godfrey joined us a little later on and has been awesome to work with.</p>
<p><strong>I don’t know anyone in tech who can take a break for very long! You guys are working out of Canada, do you think there are any advantages or disadvantages to setting up shop in Vancouver?</strong></p>
<p>Yes to both. Vancouver is a beautiful place to live and if you enjoy an active lifestyle then it's perfect. There's also a preposterous amount of engineering talent in this city.</p>
<p>We're missing a few things though. Namely we're short on soft-skills like marketing and advertising groups, and our funding scene is a little lacking.</p>
<p>Because of all the demand for talent a lot of big companies are setting up shop here. Amazon and Facebook are probably the two more popular shops, and then of course, there's Hootsuite.</p>
<p><strong>Right, let’s talk tech! What technology stack are you using on Caliper?</strong></p>
<p>All 3 founders are "full stack" engineers and we've used a lot of different technologies.</p>
<p>We use Javascript heavily for our client and library work, node for a lot of the networking and our "beacon" service, ruby for our backend processing and postgresql for storage.</p>
<p>A lot of the reason behind making those choices is the need for us to add features quickly and reliably - its all about using the right tool for the job.</p>
<p>Go will probably get added to our tool-belt next.</p>
<p><strong>Interesting stuff, what development environment is used when building Caliper?</strong></p>
<p>We all develop on Macs but full stack implementations run in Ubuntu VMs</p>
<p><strong>And of course one of the most important questions about your development environment - Vim or Emacs? ;-) (or something else?)</strong></p>
<p>Everyone at Caliper uses something different. Kalv and I are pretty big vim users. Godfrey uses SublimeText.</p>
<p>For our vim environment we use all the 'standard' extensions. Syntax highlighters, Command-T, NerdTree, etc.</p>
<p>I can’t say I'm religious about vim vs emacs, as I've never tried emacs seriously - we're *pretty fast* with vim.</p>
<p><strong>Did you have to face any interesting challenges when building the product?</strong></p>
<p>Quite a few.</p>
<p>Testing javascript implementations across 20 different browsers is non trivial. We're a "framework aware" service, which means we hook directly into Backbone, Ember, Angular, etc so being able to abstract things to apply to all those frameworks is interesting.</p>
<p>Scaling to handle 10MM metrics a day turned out to be the easy part. :)</p>
<p><strong>How do you handle testing that many JavaScript implementations?</strong></p>
<p>For testing, we've built a massive test suite written in qunit. We basically test across a bunch of versions of chrome, safari, IE and Firefox across Windows, OSX and Mobile Safari using the iOS simulator.</p>
<p><strong>If you could do it all again, is there anything you would change?</strong></p>
<p>I don't think so. I have this saying that's an intentionally mixed metaphor; hindsight is 50/50. You never know what could have happened and even if you had changed something there's no guarantee it would work out differently.</p>
<p><strong>That is a good way to look at things! What marketing challenges have you faced with Caliper?</strong></p>
<p>We're a developer focused product right now, so most of our marketing involves engaging developers. That can be hard to do. Luckily our customers are big fans of the product, and they help us out a ton - so I owe them for that!</p>
<p><strong>If developers want to engage with you, what is the best way for them to do that?</strong></p>
<p>We're pretty open to feedback. The two best ways to get in touch are to send an email to team@caliper.io or to hop on #caliper on irc.freenode.net</p>
<p><strong>Do you have anything interesting in the pipeline in the next few months?</strong></p>
<p>Right now Caliper is focused on stabilizing and optimizing your application from a code and reliability perspective. We monitor errors, network throughput, 3rd party APIs, etc.</p>
<p>Our most exciting feature is being able to break all that down on a per user basis. So I could click on Tony in Caliper and see all the different actions you took in the application. The features around that excite me the most!</p>
<p><strong>That is about all my questions, thanks again for answering these! Is there anything else you would like to say or add?</strong></p>
<p>Nope - thanks for taking the time!</p>
