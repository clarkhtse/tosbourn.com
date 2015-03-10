---
layout: post
status: publish
published: true
title: IE7 td colspan width 'issue'
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 430
wordpress_url: http://tosbourn.com/?p=430
date: '2011-04-21 16:57:36 +0100'
date_gmt: '2011-04-21 15:57:36 +0100'
categories:
- Development Help
tags:
- CSS
- IE7
comments: []
---
<p>Sometimes IE7 gets it right.</p>
<p>An example of this would be when you have a td with a CSS property of <em>width: 100px;</em> and apply a colspan of say 3.</p>
<p>What most browsers seem to do is take that width and multiply it by the colspan, whilst this is sometimes useful it isn't what you asked the browser to do.</p>
<p>IE7 doesn't assume anything, it applies the colspan first then looks at the CSS and says 'hold on a minute, they want this width set to 100px' and applies it.</p>
<p>In my opinion that is the way it should work and well done IE7 for not trying to second guess me.</p>
