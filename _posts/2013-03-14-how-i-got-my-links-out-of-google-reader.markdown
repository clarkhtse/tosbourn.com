---
layout: post
status: publish
published: true
title: How I got my links out of Google Reader
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1358
wordpress_url: http://tosbourn.com/?p=1358
date: '2013-03-14 09:40:13 +0000'
date_gmt: '2013-03-14 08:40:13 +0000'
categories:
- Other
tags:
- Sublime Text 2
- Regular Expressions
- Google Reader
comments: []
---
<p>I am sure by now you have heard that Google Reader is being canned later this year. Personally I have decided that I will not be looking for a replacement and will go RSS-less for a while but I did want a <a title="Link Dump of everything that was in my Google Reader" href="http://tosbourn.com/2013/03/web-stuff/link-dump-of-everything-that-was-in-my-google-reader/">link dump of every site I was monitoring</a> via RSS.</p>
<p>This post will briefly explain how I did it.</p>
<h2>Downloading The Data</h2>
<p>To download the data you need to visit <a href="https://www.google.com/takeout/">Google Takeout</a>, it will ask you to log in with your Google credentials and it will ask you what services you want to download, for our purposes we just want the Reader stuff.</p>
<p>It will download a zip file containing a load of .json files containing information on what you liked, stared, shared, people you followed, people that followed you and notes. It will also contain <strong>subscriptions.xml</strong>, this is what we want to look at.</p>
<h2>Formatting The Data</h2>
<p>If you open subscriptions.xml in your text editor of choice (mine being Sublime Text 2) you will see all your feeds ordered by the folders in which you kept them, all I wanted out of this was the URLs to the original sites I subscribed to, not their RSS feed.</p>
<p>In order to achieve this in Sublime I followed the following steps, 95% of good text editors will do the following or direct equivalents.</p>
<ol>
<li>Clicked <code>Cmd + F</code> to start looking for a string.</li>
<li>Made sure regular expression searching is turned on</li>
<li>Searched for <code>(?&lt;=htmlUrl=")(.*)(?=")</code></li>
<li>Clicked Find All</li>
<li>Cut them with <code>Cmd + X</code></li>
<li>Pasted the results into a new document</li>
</ol>
<p>That should be you!</p>
<p>To quickly explain the regular expression;</p>
<ul>
<li>The first () says I want my result to start with (but not be included in the selection) <code>htmlUrl="</code></li>
<li>The second () says I want anything here to be selected</li>
<li>The third () says I want my result to end with (but not be included in the selection) <code>"</code></li>
</ul>
<h2>Backing Up The Data</h2>
<p>Now you have this dump be sure to back it up somewhere useful. You could import them as bookmarks into your browser, put them somewhere in Dropbox, or if you are like me just dump them into a blog post.</p>
