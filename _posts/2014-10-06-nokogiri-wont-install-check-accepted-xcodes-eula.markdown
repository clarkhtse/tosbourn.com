---
layout: post
status: publish
published: true
title: Nokogiri won't install? Check that you have accepted Xcode's EULA
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2350
wordpress_url: http://tosbourn.com/?p=2350
date: '2014-10-06 12:21:50 +0100'
date_gmt: '2014-10-06 11:21:50 +0100'
categories:
- Development Help
tags:
- Nokogiri
- xCode
- Yak Shave
- EULA
comments: []
---
<p>Here is a pro tip I never thought I would need to share!</p>
<p>For Nokogiri to install on OSx out of the box it requires some of the command line tools that come with xCode. I have everything like that installed because I have had to install things like Nokogiri several times in the past.</p>
<p>Today though I was getting this error message that suggested that I didn't have those required tools installed.</p>
<pre>Building native extensions.  This could take a while...
Building nokogiri using packaged libraries.
ERROR:  Error installing nokogiri:
	ERROR: Failed to build gem native extension.

    /Users/tobyosbourn/.rvm/rubies/ruby-2.1.1/bin/ruby extconf.rb
Building nokogiri using packaged libraries.
checking for iconv.h... *** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of necessary
libraries and/or headers.  Check the mkmf.log file for more details.  You may
need configuration options.
</pre>
<p>10 minutes of yak shaving later and I decided to open up xCode to see what the craic was, turns out a point release had been downloaded and installed and came with a new EULA, as soon as I accepted this I was able to install the nokogiri gem successfully!</p>
