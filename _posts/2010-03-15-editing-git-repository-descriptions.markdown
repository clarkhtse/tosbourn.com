---
layout: post
status: publish
published: true
title: Editing Git Repository Descriptions
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 211
wordpress_url: http://www.tosbourn.com/?p=211
date: '2010-03-15 13:39:02 +0000'
date_gmt: '2010-03-15 12:39:02 +0000'
categories:
- Development Help
tags:
- Git
- Repository
comments: []
---
<p>It was annoying me that when viewing my repositories online the descriptions for them all were the generic 'Unnamed repository; edit this file 'description' to name the repository.'</p>
<p>It doesn't really tell you in any tutorial what you need to do when setting up a repository to get a description (or at least any I have followed) but the fix is very simple.</p>
<p>In the your git repository you should see a text file named description.</p>
<p>Edit it with your text editor of choice and whatever you have as the contents will be your repository description.</p>
<p><code>vi gitRepository.git/description</code></p>
<p>Done!</p>
