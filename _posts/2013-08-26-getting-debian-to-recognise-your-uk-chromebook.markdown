---
layout: post
status: publish
published: true
title: Getting Debian to recognise your UK Chromebook
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1632
wordpress_url: http://tosbourn.com/?p=1632
date: '2013-08-26 09:12:17 +0100'
date_gmt: '2013-08-26 08:12:17 +0100'
categories:
- Development Help
tags:
- Chromebook
- Keyboard
- Debian
comments: []
---
<p>I am running Debian on my Chromebook (via Crouton), and one of the issues I had to deal with when I set up Debian initially was that the keyboard layout is set to English(US). In my experience this normally means very minor things normally around where the @ symbol lives.</p>
<p>With the Chromebook however there seems to be way more keybindings that were just different, and non-obvious, so the task of getting the keyboard setup correctly quickly took priority. Here is how I did it.</p>
<ol>
<li>Click on Applications Menu</li>
<li>Go to Settings &gt; Keyboard</li>
<li>Click on Layout</li>
<li>Untick 'Use System Defaults'</li>
<li>Under Keyboard Layout click 'Add'</li>
<li>Find English (UK), select it and click 'OK'</li>
<li>Click on English (US) in your list and click 'Delete'</li>
</ol>
<p>This should be you, keys I would check are |\#~, these all seemed to be the most messed up for me.</p>
