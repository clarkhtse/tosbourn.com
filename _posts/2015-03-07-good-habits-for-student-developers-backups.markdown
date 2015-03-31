---
layout: post
status: publish
published: true
title: Good Habits for Student Developers - Backups
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2637
wordpress_url: http://tosbourn.com/?p=2637
date: '2015-03-07 00:11:54 +0000'
date_gmt: '2015-03-06 23:11:54 +0000'
categories:
- Development Help
tags:
- Backups
- '365'
- Students
---
Sometimes the hardest or most frustrating part of development isn't the code, the algorithms, or even other people! Sometimes it can be some of the other tasks a professional developer needs to be doing in order to be doing their job correctly.

I want to talk with you about three tasks that are very important that aren't development. Backups, Documenting, and [Time Keeping](/good-habits-for-student-developers-time-keeping/).

<p>I don't want to make this a massive article so I am going to split this into a series of three.</p>
<p>I have two disclaimers, the first is that I graduated university years ago and they may well teach these three topics incredibly well now to all their Computer Scientists. The second is that even though I have been working as a professional developer for several years now I am continually learning and finding out better ways to do things.</p>
<p>With those in mind onto our first topic, backups.</p>
<h2>Backups</h2>
<p>Having stuff die on you is really freaking annoying when it is your music collection, your questionably acquired movies or whatever. When it is your livelihood it can be crippling. It isn't just the time invested that you may have lost forever, it is the time you are going to need to spend to get your machine back up to speed to allow you to be productive again.</p>
<p>There are two aspects regarding backing up that are important to get good at.</p>
<h3>Backing up your computer</h3>
<p>All code on your computer needs to be version controlled, I have written <a href="http://thetomorrowlab.com/2015/02/why-web-developers-should-use-version-control/">at length about this</a>. If your college hasn't taught you the virtues of version control you need to take it upon yourself to learn how to use it.</p>
<p>Aside from code I use three things to back up my machine.</p>
<ul>
<li><a href="https://db.tt/IlOuq8C">Dropbox</a> – For keeping files I want access to safe and somewhere that is easy for me to access from all my machines and on the web.</li>
<li><a href="https://secure.backblaze.com/r/01tl1n">BackBlaze</a> - Backs up everything else that Dropbox doesn't. This is completely remote and worth the annual fee. I have <a href="http://tosbourn.com/backblaze-part-great-backup-solution/">written up about how much I love BackBlaze</a>.</li>
<li>TimeMachine – This is a tool specific to Apple's OSx operating system. This isn't remote but allows me to do fast local backups.</li>
</ul>
<h3>Backing up your website data</h3>
<p>If you are using version control locally then code getting messed up on your server isn't the worst thing in the world, you will be able to quickly recover from that. The thing you will need to consider is backing up the data that users of your website or application generate.</p>
<p><strong>You will destroy data you weren't meant to</strong>. Trust me. All the best people in the business have. Sometimes the only way you know to triple check any type of destroy command is by very bad stuff happening.</p>
<p>Most hosting packages come with backups, if they don't find another host. I currently host my websites with <a href="http://www.bigwetfish.co.uk/whmcs/aff.php?aff=264">Big Wet Fish</a> who have some great backup plans. I also use <a href="http://heroku.com">Heroku</a> who likewise have great backup functionality.</p>
<p>You want something you can set and forget.</p>
<p>You should also set a reminder for yourself to check your backups once every 6 months, just to make sure they are backing up what you think they are!</p>
<h2>Backup Plans</h2>
<p>I have listed some tools here, and given you a high level opinion on what I think is important to backup. The important take away is that you need to be aware that backups are super important and you need to be thinking about the most painless way to put a plan in place.</p>
<p>Some people will tell you that you need hourly backups of your database, others will say that is excessive and a waste of hard disk space. The important thing is that you have considered the idea of backups and can explain your point of view one way or another.</p>
<h2>Wrapping up</h2>
<p>One thing you need to take into account when thinking about backups is that you need to value your time. If something is going to take you 3 hours to fix because you didn't have a good backup plan in place you need to be aware that this is lost time and lost money. Even if you charge yourself out at £20 an hour you might find an annual plan of £50 suddenly makes sense if you are going to waste three hours of your time not developing.</p>
<p>Hopefully this has been useful. If you have any questions about backups please comment – there are seriously no stupid questions.</p>
