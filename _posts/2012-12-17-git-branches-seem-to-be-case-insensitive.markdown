---
layout: post
status: publish
published: true
title: Git branches seem to be case insensitive
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1174
wordpress_url: http://tosbourn.com/?p=1174
date: '2012-12-17 12:18:02 +0000'
date_gmt: '2012-12-17 11:18:02 +0000'
categories:
- Development Help
tags:
- Git
- Github
- Branching
comments:
- id: 466
  author: amn41
  author_email: alan.nichol@gmail.com
  author_url: ''
  date: '2014-05-08 18:13:00 +0100'
  date_gmt: '2014-05-08 17:13:00 +0100'
  content: Thanks for this!
---
<p>Git branches appear to be case insensitive, which isn't a problem in and of itself, but if you clone a remote branch from github like this:</p>
<p><code>git checkout -b my_new_branch /origin/My_New_Branch</code></p>
<p>Git will see your new branch as <code>my_new_branch</code><sup>*</sup> and when you pull it will check <code>origin/My_New_Branch</code> which is totally correct and sane, but if you do a push it seems to want to push to a new branch in github called <code>my_new_branch</code> which will get super confusing if multiple people need to access this branch.</p>
<p><strong>The ideal fix for this is prevention</strong> - just don't create a new local branch with a different name to your remote branch, but let's say you do?</p>
<p>Creating a new branch with the correct case will not work because git is case insensitive and will see both <code>my_new_branch</code> and <code>My_New_Branch</code> as the same thing, instead you need to rename your current branch using a middle step. Luckily like most things in git this is very straightforward;</p>
<p><code>git branch -m my_new_branch tmp_branch</code> (will rename your lowercase branch to tmp_branch)</p>
<p><code>git branch -m tmp_branch My_New_Branch</code> (will rename to your desired CamelCase branch!)</p>
<p>Now your pushes should go to the correct branch.</p>
<p><small><sup>*</sup>Disclaimer - My_New_Branch is a terrible name for a branch, always be descriptive and imagine you are naming it for someone else who doesn't know the project to read.</small></p>
