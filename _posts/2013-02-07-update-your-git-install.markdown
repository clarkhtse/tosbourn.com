---
layout: post
status: publish
published: true
title: Update your Git install
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1305
wordpress_url: http://tosbourn.com/?p=1305
date: '2013-02-07 10:51:26 +0000'
date_gmt: '2013-02-07 09:51:26 +0000'
categories:
- Development Help
tags:
- Git
- Upgrading
comments: []
---
<p>We are so used to applications on our phones and computers shouting at us every two seconds to update them to the latest version that we can become blind to new releases of software that don't ram the fact they are updated down your throat.</p>
<p>Git is a fine example of this, like most command line tools it will happily sit on whichever version you happen to have installed way back when, and that is fine, except for if you installed Git a year or more ago you might be missing out on some new features and bug fixes.</p>
<p>To find out what version of Git you are running simply type <code>git --version</code> into your command line, I am going to guess it is sitting at 1.7.x.</p>
<p>As of writing the most recent stable version is <b>1.8.1.2</b>, if you want to see what the difference is between your version and the current version take a look at this <a href="http://mac.softpedia.com/progChangelog/Git-Changelog-34991.html">Git Changelog</a>.</p>
<p>How you installed Git will have some influence on how you update it, on OSx I think Git comes pre-installed so what I have had to do in the past is download the .dmg file from the <a href="http://git-scm.com/">Git website</a> and install the latest version, making sure to add the install location of the new Git to my PATH variable so it is seen as the version of Git to use.</p>
