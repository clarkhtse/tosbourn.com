---
layout: post
status: publish
published: true
title: If you store WordPress code on Github think about your wp-config.php
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1271
wordpress_url: http://tosbourn.com/?p=1271
date: '2013-01-25 14:25:59 +0000'
date_gmt: '2013-01-25 13:25:59 +0000'
categories:
- Other
tags:
- Wordpress
- Security
- Github
- Fail
- Passwords
comments: []
---
<p>If you store WordPress code on Github inside of a public repository all your code is public. Most people know and accept this, but people either don't realise that their database credentials get stored inside the php file <code>wp-config.php</code> or they do and forget to exclude it from their repository.</p>
<p>This means that if you do a simple Google search for <kbd>site:github.com master/wp_config.php password blob DB_PASSWORD</kbd> you will find a whole rake of folk with their passwords on display.</p>
<p>Obviously it is impossible to tell if they are just sample details or real details, but it is still crumby practice and if you do it you<strong> really need to stop now</strong>.</p>
<p>I will be contacting people I find to let them know, but please pass this message on to any WordPress/GitHub users you know.</p>
