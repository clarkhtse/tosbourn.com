---
layout: post
status: publish
published: true
title: Deploying a particular branch to Engine Yard from the command line
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1568
wordpress_url: http://tosbourn.com/?p=1568
date: '2013-06-25 08:28:06 +0100'
date_gmt: '2013-06-25 07:28:06 +0100'
categories:
- Development Help
tags:
- Git
- Deployment
- Engine Yard
comments: []
---
<p>I wouldn't recommend jumping between different branches too often when you are deploying, it is too easy to forget which branch you actually want to deploy and that could be disastrous, but on occasion it just makes sense.</p>
<p>The command you need to run would be something like this;</p>
<p><code>ey deploy -e demo -r my_awesome_branch</code></p>
<p><code>ey</code> just calls engine yard, <code>deploy</code> tells engine yard that we want to deploy something, <code>-e</code> tells it what environment to deploy it to, and <code>-r</code> is optional and stands for ref, this tells engine yard which branch, tag or SHA to deploy.</p>
<p>&nbsp;</p>
