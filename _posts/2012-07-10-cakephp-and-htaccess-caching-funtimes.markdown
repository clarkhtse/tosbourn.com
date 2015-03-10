---
layout: post
status: publish
published: true
title: CakePHP and htaccess caching funtimes
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1074
wordpress_url: http://tosbourn.com/?p=1074
date: '2012-07-10 14:59:51 +0100'
date_gmt: '2012-07-10 13:59:51 +0100'
categories:
- Development Help
tags:
- CakePHP
- htaccess
- Caching
comments: []
---
<p>I wanted to fire up a quick post about my CakePHP and htaccess caching issue — So I was working on a CakePHP project and I was pulling my hair out wondering why a development site was redirecting to a production site, the issue was quickly narrowed down the the .htaccess file which was uploaded to the development area in error — it contained some redirect rules that were kicking in.</p>
<p>So I logged into the development machine and removed the offending htaccess rules, refreshed the page but the issue was still happening.</p>
<p>The reason was that the development server had also had the config file for the production server which has CakePHP caching turned on.</p>
<p>The main take away here is that your .htaccess can potentially get cached by CakePHP, this isn't something I had thought would happen and until there is a problem you might never consider this as an issue.</p>
<p>The second take away is that the code shouldn't have needed to be kept separate between development and production, this is something I am going to look at improving on some projects.</p>
<p>In my case the fix was to clear the cache, once Cake had picked up the new .htaccess file everything was grand again.</p>
<p>Going forward I am going to make sure that when I make changes any files on a CakePHP project I will refresh the cache, just to play it safe.</p>
<p>&nbsp;</p>
