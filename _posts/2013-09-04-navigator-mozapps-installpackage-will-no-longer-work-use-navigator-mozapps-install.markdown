---
layout: post
status: publish
published: true
title: navigator.mozApps.installPackage will no longer work use navigator.mozApps.install
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1650
wordpress_url: http://tosbourn.com/?p=1650
date: '2013-09-04 16:04:52 +0100'
date_gmt: '2013-09-04 15:04:52 +0100'
categories:
- Development Help
tags:
- Firefox OS
- Manifest
comments:
- id: 449
  author: abral
  author_email: abral@email.it
  author_url: ''
  date: '2014-04-22 21:05:00 +0100'
  date_gmt: '2014-04-22 20:05:00 +0100'
  content: installPackage is used to install packaged apps, install is used to install
    hosted apps.
---
<p>Pretty much as the title says really!</p>
<p>If you are building a webapp for Firefox OS it used to be that to install the manifest file you would call <code>navigator.mozApps.installPackage('path/to/manifest')</code> but this has been changed to just be <code>navigator.mozApps.install('path/to/manifest')</code>.</p>
<p>This tripped me up recently as I was following an old guide and I couldn't work out why something that I was positive worked before no longer worked!</p>
<p>I think this syntax is a lot cleaner.</p>
