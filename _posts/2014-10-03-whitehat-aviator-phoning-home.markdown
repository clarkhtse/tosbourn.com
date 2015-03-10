---
layout: post
status: publish
published: true
title: WhiteHat Aviator Phoning Home?
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2348
wordpress_url: http://tosbourn.com/?p=2348
date: '2014-10-03 16:16:46 +0100'
date_gmt: '2014-10-03 15:16:46 +0100'
categories:
- Other
tags:
- Whitehat
- Aviator
comments:
- id: 625
  author: N^NN^
  author_email: nw446sn66u@yahoo.com
  author_url: ''
  date: '2014-10-11 14:13:00 +0100'
  date_gmt: '2014-10-11 13:13:00 +0100'
  content: How to COMPLETELY disable/uninstall the "PDF Viewer" extension on Aviator?
    When I disallow that extension from working in incognito, the corresponding checkbox
    is checked again! I want to directly download PDF files from Aviator without opening
    the annoying PDF Viewer extension.
- id: 626
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-10-13 08:41:00 +0100'
  date_gmt: '2014-10-13 07:41:00 +0100'
  content: Because I don't use the browser day in day out I am not sure sorry, someone
    else might now.
---
<p>Recently I was contacted by someone who wishes to remain anonymous (which is fair enough!) about my <a title="Review: Whitehat Aviator" href="http://tosbourn.com/review-whitehat-aviator/">review of WhiteHat Aviator</a>.</p>
<p>In the email I was asked to look at how WhiteHat Aviator phones home. The person who contacted me was concerned that they had noticed network activity coming roughly every five hours from Aviator to some WhiteHat servers.</p>
<p>My gut reaction was this was likely just the service phoning home to look for updates, but not knowing the best practice for doing this on a Mac I decided to email WhiteHat and ask about why Aviator phones home, I had mentioned this was in response to an email I had received from a concerned user.</p>
<p>I wanted to share parts of their response because I think it clears up any issues;</p>
<blockquote><p>Here's how it works - every 5 hours the browser calls back to our server with a non-unique query so we can't correlate/track our users. We spent a lot of time working on this to try to limit our ability to track users, because browsers like Chrome phone home with the machine-ID and user-ID of the system for every update and that wasn't something we were willing to do.</p>
<p>If the file that is downloaded says there is an update the browser will automatically fetch and barring any signing issues or corruption in the file it will install it for use the next time the user downloads the browser. Other browsers have paved the way in this regard, and find that it is significantly safer to always keep the user updated, since the majority of features we launch are security related anyway.</p>
<p>The purpose of our browser was to be used by the common person, not by the security pro or privacy nut. They have the technical chops to use Tor (in a safe manner, which isn't actually very easy to do) or modify their own browser. The average person doesn't have that ability, so this browser is intended to give them the right training wheels to make sure<br />
they don't have issues. We always allow our users to disable plugins, but if they remove them the browser will just re-download them so that doesn't make much sense. Each plugin has been chosen specifically to achieve better usability and higher security. For example, we had to ship with UA spoofer, because too many sites are poorly programmed and don't know that other browsers exist and don't have a graceful failure mode. PDF.js was essential, because it's much safer, from what we can tell thus far, than Adobe's PDF viewer - time will tell if that was an incorrect assumption but other browsers are betting on the same thing, so I think it's a safe bet. Disconnect is the plugin that supports ad-blocking and blocking of tracking pixels which speeds up the user experience and speeds up increases security in the process. Those are the only plugins we ship with - if the user has others, that didn't come from us.</p>
<p>The end result here, is that I think this user is conflating privacy with security, and while we are a much more private browser than most, we would never claim to be 100% private, because we have to allow our users to get updates. If 100% privacy assurance is the goal, Tor browser is the one of choice - though, there are many security and privacy pitfalls due to compromised exit nodes, which is why I would never recommend it to the Masses."</p></blockquote>
<p>If you are a concerned user after hearing or experiencing the phoning home, then I hope this clears it up for you :-)</p>
