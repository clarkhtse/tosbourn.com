---
layout: post
status: publish
published: true
title: Working out which merge to keep in Git
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1470
wordpress_url: http://tosbourn.com/?p=1470
date: '2013-05-02 15:08:59 +0100'
date_gmt: '2013-05-02 14:08:59 +0100'
categories:
- Development Help
tags:
- Git
- Blame
- Merge
comments: []
---
<p>Sometimes in Git we will do a merge that will need manual intervention.</p>
<p>If you are merging your own stuff in with your own stuff then most of the time you are going to know which bit of code to keep or if to keep them both.</p>
<p>Things get interesting when either of the following two cases apply;</p>
<ul>
<li><span style="line-height: 1.714285714; font-size: 1rem;">You are merging in someone else's code</span></li>
<li><span style="line-height: 1.714285714; font-size: 1rem;">You can't remember why you had written the code that is causing the issue.</span></li>
</ul>
<p>Both of these cases can be solved by a using git's <a href="https://www.kernel.org/pub/software/scm/git/docs/git-blame.html" target="_blank">blame</a>.</p>
<p><code>git blame</code> will show you a line by line breakdown of who wrote what line of code and as part of what commit and why this is useful for helping with merges is that it will;</p>
<ul>
<li><span style="line-height: 14px;">Let you know who you need to contact to discuss what needs to happen with this merge if it is non-obvious.</span></li>
<li>Give you a commit hash that you can then query to find out the bigger picture and the context of the smaller change that is currently causing you issues.</li>
</ul>
<p>To run <code>git blame</code> on a file simply call <code>git blame my_file_name.rb</code> and the output will be the contents of the file with each line prepended with the commit hash, the commiter and the the date and time it was commited.</p>
