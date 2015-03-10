---
layout: post
status: publish
published: true
title: InFrame - Dynamic iFrame creation with jQuery
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 195
wordpress_url: http://www.tosbourn.com/?p=195
date: '2009-11-27 23:27:18 +0000'
date_gmt: '2009-11-27 22:27:18 +0000'
categories:
- Development Help
tags:
- Development
- jQuery
- iFrame
comments: []
---
<p>jQuery spends a lot of time impressing the shit out of me, one example of it doing it recently is with <a href="http://www.vileworks.com/inframe-keep-the-demos-inside-the-page-with-jquery">Vile Work's inFrame</a> (one person has reported an issue with this site and viruses, I cannot replicate though.).</p>
<p>What this plugin does is capture any links containing a certain class and instead of having them display in the current window it will create an iFrame on the fly for the content to display into.</p>
<p>We all know that iFrames are bad because they hide stuff from crawlers and different accessibility tools, however one of the really smart things about this is that because it looks for links of a certain class anyone coming along without JavaScript installed (say, a search engine for example) will just follow the link as normal with no negative effect.</p>
<p>I can see loads of potential uses for this tool and look forward to playing with it in an actual project.</p>
