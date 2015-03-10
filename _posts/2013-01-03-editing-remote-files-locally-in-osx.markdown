---
layout: post
status: publish
published: true
title: Editing remote files locally in OSx
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1212
wordpress_url: http://tosbourn.com/?p=1212
date: '2013-01-03 10:44:50 +0000'
date_gmt: '2013-01-03 09:44:50 +0000'
categories:
- Development Help
tags:
- Server
- Local
- Text Editor
- SSH
comments: []
---
<p>Sometimes we spend so much time with our local text editor that when we need to jump onto the server to edit files (apache config files, for example) we have to stumble around with VIM or Emacs (I should state, both are fine editors — all I am saying is if it isn't what you use day in day out they will not feel as comfortable as what you use).</p>
<p>Luckily if you use OSx there is a way you can map your remote server to allow you to edit files locally and have the changes saved automatically on the remote machine, and setting it up is really straight forward.</p>
<p>The first thing you will want is to set up SSH key authentication — I will not cover that here but if you have your machine talking to Github then you already have your public key so all you need to do is add it onto the list of allowed keys on the remote machine, google will help.</p>
<p>Next you want to install <a href="http://osxfuse.github.com/">FUSE</a> (http://osxfuse.github.com/) this is a package that once installed allows you access to a terminal command that we will use to set up the pairing.</p>
<p>Once installed run the following in terminal;</p>
<p><kbd>mkdir ~/my_server<br />
</kbd><kbd>sshfs username@my_server.com:/directory/i/want/to/map ~/my_server</kbd></p>
<p>Which should create the mapping.</p>
<p>Right now I don't see a way of viewing this folder inside of finder (if you know, please <a href="https://twitter.com/tosbourn">tweet me</a>!) but you should now be able to access your server by going to ~/my_server on your local machine, then running something like <kbd>open .</kbd> to open the folders up in finder.</p>
