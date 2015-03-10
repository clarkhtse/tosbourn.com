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
comments:
- id: 703
  author: melissakeizer
  author_email: melissakeizer1@gmail.com
  author_url: https://melissakeizer.exposure.co/
  date: '2015-03-07 12:03:00 +0000'
  date_gmt: '2015-03-07 11:03:00 +0000'
  content: 'Great post Toby, I always find it interesting to read how others back
    up their files. I use GitHub for my web projects and time machine for local backups
    of everything, but all of my other important files are on two external HDs in
    my house. I know this is just a disaster waiting to happen! Been considering BackBlaze
    for a while, just trying to justify the expense to myself. You''d recommend it
    then? I have about 1TB worth of photos and other files to backup! '
- id: 704
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-03-08 12:07:00 +0000'
  date_gmt: '2015-03-08 11:07:00 +0000'
  content: I would recommend it yeah – It really is a set and forget thing and saved
    my ass when my old MBP decided it didn't want to live anymore.
- id: 705
  author: Michael Bole
  author_email: penguin_soldier5@hotmail.com
  author_url: ''
  date: '2015-03-09 12:39:00 +0000'
  date_gmt: '2015-03-09 11:39:00 +0000'
  content: Great advice. The amount of students that lost their work during university
    was crazy. They had to learn the hard way.
- id: 706
  author: Scott Edgar
  author_email: scott@scottedgar.co.uk
  author_url: ''
  date: '2015-03-09 12:42:00 +0000'
  date_gmt: '2015-03-09 11:42:00 +0000'
  content: |-
    Great post. When I was studying, none of this was even on the agenda but now I use a combination of things. For web projects I've only just started using Github. I know, shame on me, but I'm old school. We only used Notepad and FTP back when I started! I'm also a big fan of WPBackup, if Wordpress is your CMS of choice.

    Locally, I've actually moved most of my files to the cloud, using Google+ for images, Google Drive for bits and pieces and a combination of Dropbox and Box.com for bigger artwork files, design PDFs etc. It keeps everything up to date plus it's dead handy for accessing anything on the go.
- id: 707
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-03-09 18:06:00 +0000'
  date_gmt: '2015-03-09 17:06:00 +0000'
  content: Unfortunately I am sure many didn't actually learn and will repeat the
    same mistakes again!
- id: 708
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-03-09 18:07:00 +0000'
  date_gmt: '2015-03-09 17:07:00 +0000'
  content: How are you finding box? I had a very quick play when it was in early access
    and thought it was grand but not significantly better than dropbox.
- id: 709
  author: Scott Edgar
  author_email: scott@scottedgar.co.uk
  author_url: ''
  date: '2015-03-09 18:11:00 +0000'
  date_gmt: '2015-03-09 17:11:00 +0000'
  content: Seems to sync a lot slower than Dropbox and is a bit of a resource hog.
    I mainly use it because I signed up during an offer period and got a free 50GB
    account. Dropbox is definitely a much better experience.
---
<p>Sometimes the hardest or most frustrating part of development isn't the code, the algorithms, or even other people! Sometimes it can be some of the other tasks a professional developer needs to be doing in order to be doing their job correctly.</p>
<p>I want to talk with you about three tasks that are very important that aren't development. Backups, Documenting, and Timekeeping.</p>
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
