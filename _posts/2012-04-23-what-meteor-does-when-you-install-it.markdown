---
layout: post
status: publish
published: true
title: What Meteor does when you install it
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1003
wordpress_url: http://tosbourn.com/?p=1003
date: '2012-04-23 22:58:31 +0100'
date_gmt: '2012-04-23 21:58:31 +0100'
categories:
- Development Help
tags:
- Meteor
comments: []
---
<p>I have been playing about with <a href="http://meteor.com/">Meteor</a> recently and I am going to start blogging about different cool things you can do with it.</p>
<p>The first pretty cool thing which I haven't seen any applications do before is leverage the power of the pipe for installing Meteor.</p>
<p>The command given on the site to get you up and running is:</p>
<pre>curl install.meteor.com | sh</pre>
<p>If you are not familiar with the command line this can look a little messy, but this is actually very elegant install solution, it makes sure all new installs have the most bang up-to-date version and uses a shell script for the install, which is supported by a large amount of machines.</p>
<p>The command is divided up into two sections, the section before the pipe ('|') and the section after it.</p>
<p>The section before uses a command that grabs the content from a URL and displays it (in this case the content of install.meteor.com).</p>
<p>Only the pipe tells us that whatever output that first command gives to give it to the second command, so it passes the output of install.meteor.com to the sh command instead of displaying it.</p>
<p>The sh command calls a primitive language used by most *nix based systems. This executes the contents of install.meteor.com allowing the rest of the program to be installed.</p>
<p>If you want to see exactly what is being installed just browse on over to <a href="http://install.meteor.com">install.meteor.com</a> to take a look.</p>
<p>Normally to install things you need to download the .sh file, run a change of permissions to allow the file to be executed, and then call it - this method gets around all this in one nice neat line.</p>
<p>You will see for yourself how awesome this platform is to develop on when I start posting some examples and tutorials, but lets just say that when they have made the install this elegant, you can be sure they have made the rest of it just as well.</p>
