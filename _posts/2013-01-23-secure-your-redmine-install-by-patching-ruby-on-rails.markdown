---
layout: post
status: publish
published: true
title: Secure your Redmine install by patching Ruby on Rails
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1266
wordpress_url: http://tosbourn.com/?p=1266
date: '2013-01-23 16:34:12 +0000'
date_gmt: '2013-01-23 15:34:12 +0000'
categories:
- Other
tags:
- Redmine
- Ruby
- Ruby on Rails
comments:
- id: 292
  author: Gary Barclay
  author_email: badimba@gmail.com
  author_url: ''
  date: '2013-11-28 19:10:00 +0000'
  date_gmt: '2013-11-28 18:10:00 +0000'
  content: Thanks for this info...Redmine security seems to be a bit of "finger in
    the air" type scenario with very few advisories.
---
<p>Fairly recently the Ruby on Rails community <a href="http://weblog.rubyonrails.org/2013/1/8/Rails-3-2-11-3-1-10-3-0-19-and-2-3-15-have-been-released/">released some patches to fix some rather serious security problems</a> with Rails. If you haven't patched yet you really, really should.</p>
<p>The only application <a href="http://piercecommunications.co.uk">we</a> had on a public server was our Redmine installation, one of the issues with Redmine is that is can be pretty picky about which versions of Rails it will play with so I was a little worried about updating it and potentially breaking everything.</p>
<p>If you followed my guide for <a title="Setting up Redmine from a blank Ubuntu install" href="http://tosbourn.com/2012/09/linux/setting-up-redmine-from-a-blank-ubuntu-install/">installing Redmine</a> then you are in luck, to patch Rails is incredibly easy. Shut down Redmine and run the following;</p>
<p><code>gem update</code></p>
<p>That is it! It updates all the gems installed to the latest versions (in the case of 3.2.x it took me to 3.2.11). Turn Redmine back on and enjoy the project management goodness knowing your Rails setup is nice and patched.</p>
