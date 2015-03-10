---
layout: post
status: publish
published: true
title: Open a file in Github from your command line
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1737
wordpress_url: http://tosbourn.com/?p=1737
date: '2013-11-13 13:51:39 +0000'
date_gmt: '2013-11-13 12:51:39 +0000'
categories:
- Development Help
tags:
- Command Line
- Github
- Gists
comments: []
---
<p>I wanted to share a <a href="https://gist.github.com/richardmcmillen-examtime/7448300">gist</a> that a <a href="https://twitter.com/rickysaystweet">colleague</a> at ExamTime has written and shared up on Github.</p>
<p>He wanted to be able to quickly get access to a file on Github without wanting to jump around the Github website, so he wrote a script he can run from inside a git repository on your terminal.</p>
<p>If you add it into your bin directory as an executable (or add it into your path or whatever way you crazy kids want to handle it) and call it say repo then you can call the following;</p>
<p><code>$ repo -f app/controllers/my_awesome_controller.rb</code></p>
<p>And it will take you to the master branch version of that file, if you want to see another branch then you can specify that as well by typing in;</p>
<p><code>$ repo -b my_cool_branch -f app/controllers/my_awesome_controller.rb</code></p>
<p>I am sure plenty of people (including myself) will find this super handy.</p>
