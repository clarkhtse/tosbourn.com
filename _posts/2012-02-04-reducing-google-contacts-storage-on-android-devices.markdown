---
layout: post
status: publish
published: true
title: Reducing Google Contacts storage on Android devices
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 827
wordpress_url: http://tosbourn.com/?p=827
date: '2012-02-04 20:18:35 +0000'
date_gmt: '2012-02-04 19:18:35 +0000'
categories:
- Other
tags:
- Google
- Android
- Contacts
comments:
- id: 152
  author: Donna
  author_email: donna@netmums.com
  author_url: ''
  date: '2012-06-29 17:32:00 +0100'
  date_gmt: '2012-06-29 16:32:00 +0100'
  content: Thank you so much for this, the low storage icon has been driving me nuts
    for months and this has reduced my contacts from 11/87MB to 878KB.  Looking forward
    to other blogs on the topic of reducing phone storage if you ever get time.
- id: 153
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-06-29 20:21:00 +0100'
  date_gmt: '2012-06-29 19:21:00 +0100'
  content: I am very glad you found it useful Donna!
- id: 392
  author: JP V
  author_email: jp.velasco@gmail.com
  author_url: ''
  date: '2014-01-25 04:22:00 +0000'
  date_gmt: '2014-01-25 03:22:00 +0000'
  content: my wife's GS4 has the same problem. in her case a whopping 6GB size of
    Contacts Storage file. Takes a LOOOOONG time to load Contacts. Am doing this now.
- id: 393
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-25 10:24:00 +0000'
  date_gmt: '2014-01-25 09:24:00 +0000'
  content: Let me know how you get on :-)
- id: 461
  author: Nik
  author_email: njain73@gmail.com
  author_url: ''
  date: '2014-04-30 09:20:00 +0100'
  date_gmt: '2014-04-30 08:20:00 +0100'
  content: Simplest solution but needs to be repeated every few months - 'clear dumstate/logcat'
    .. Dial *#9900# and select the second option. This typically frees up 50-75% of
    your internal storage :)
- id: 488
  author: Kristof Van Tomme
  author_email: kristof@pronovix.com
  author_url: ''
  date: '2014-05-25 00:12:00 +0100'
  date_gmt: '2014-05-24 23:12:00 +0100'
  content: I keep having the same problem, but for me contact data eventually takes
    up over 1GB of space. I think this might be an issue when synching with 2 google
    accounts.
---
<p>After a couple of months of use my HTC phone running Android was constantly telling me that my phone storage was running low.</p>
<p>I have tried several methods of reducing the files kept on the phone storage (which I will blog about sometime) but one of the methods that I want to discuss today is to free up some of the Google Contact storage.</p>
<p>In order to use the Market on your Android you need a Google account, like a lot of people I had my Google account well before I had my phone as I use Googlemail so when setting up my phone naturally these were the credentials I would put in.</p>
<p>A slightly annoying feature of Android is that it will automatically sync your Google contacts to your phone without allowing you not to, and to make matters worse it has to be your internal phone storage, not any SD cards you happen to use.</p>
<p>I have looked around for several solutions and at the moment the best practice seems to be to set up a dummy Google account and use that for all your Android syncing.  Initially this is what I was going to do but I started thinking that perhaps the issue isn't that my contacts are now on my phone (I mean, that makes sense, right?) it is that perhaps I have too many contacts.</p>
<p>Googlemail has been setup to automatically save contact information for anyone you email and over the years I have used my Googlemail account to do mass mailouts about various projects I am involved in and have basically amassed a massive amount of contact information that I will never really use again.</p>
<p>It is time for a cull.</p>
<p>The first step is of course to backup your contacts, this is very easy.</p>
<ol>
<li>Log into your Googlemail Account</li>
<li>Select 'Contacts' from the dropdown menu on the left.</li>
<li>Under 'More' select Export</li>
<li>Select how you want to export them (I picked Google cvs)</li>
</ol>
<p>Having a backup means I always have a fallback should I really really need to dig out someones email address, but the thing is if I have spoken to them in the past I most likely have an email in my account with their details in it - I can't see me needing to import my contacts any time soon.</p>
<p>The next step is to then delete your contacts.</p>
<p>The only way I found to do this was in your Contacts area to select the check all tickbox and under 'More' select Delete Contacts - this could be slow enough if you have thousands like I do, but it gets the job done.</p>
<p>Finally (kind of) you want to sync your new empty contacts folder.</p>
<p>You should be able to do this in 'Settings' on your Android but for some reason mine wouldn't do a proper sync until I turned my phone off and on again - even then the contacts file would sync but not remove anything.</p>
<p>So I backed up my contacts to my SD card, I did this by going to;</p>
<ol>
<li>People</li>
<li>Hitting Menu</li>
<li>Selecting Import/Export</li>
<li>Exporting all contacts (sim and phone) to SD</li>
</ol>
<p>Then I went in and deleted the data associated with my contact card;</p>
<ol>
<li>Settings</li>
<li>Applications</li>
<li>Manage Applications</li>
<li>Finding Contacts Storage</li>
<li>Deleting the data.</li>
</ol>
<p>Then I re-imported the exported contacts in again.</p>
<p>Before doing this my contacts file was 19.4MB after it was 1.72MB and the notification about low phone storgage has well and truly gone.</p>
<p><strong>This shouldn't be the way things needed to be done</strong> - but needs must!</p>
<p>If you have any other ways of getting around this auto sync that doesn't involve removing contacts or having a dummy account I would love to hear it.</p>
