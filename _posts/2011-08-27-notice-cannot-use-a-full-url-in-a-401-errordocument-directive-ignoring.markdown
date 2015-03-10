---
layout: post
status: publish
published: true
title: '[notice] cannot use a full URL in a 401 ErrorDocument directive --- ignoring!'
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 528
wordpress_url: http://tosbourn.com/?p=528
date: '2011-08-27 23:18:09 +0100'
date_gmt: '2011-08-27 22:18:09 +0100'
categories:
- Other
tags:
- Apache
- Error Logs
- Grep
- Find
- '401'
comments:
- id: 114
  author: El Duderino
  author_email: nobody@nowhere.com
  author_url: ''
  date: '2012-03-02 02:03:00 +0000'
  date_gmt: '2012-03-02 01:03:00 +0000'
  content: |-
    Guess I should have read on a little further:
    Note that when you specify an ErrorDocument that points to a remote URL (ie. anything with a method such as http in front of it), Apache will send a redirect to the client to tell it where to find the document, even if the document ends up being on the same server. This has several implications, the most important being that the client will not receive the original error status code, but instead will receive a redirect status code. This in turn can confuse web robots and other clients which try to determine if a URL is valid using the status code. In addition, if you use a remote URL in an ErrorDocument 401, the client will not know to prompt the user for a password since it will not receive the 401 status code. Therefore, if you use an ErrorDocument 401 directive then it must refer to a local document.
---
<p>I was skimming through my Apache Error Log today (as one does of a Saturday evening) and was finding a load of entries with.</p>
<blockquote><p>[notice] cannot use a full URL in a 401 ErrorDocument directive --- ignoring</p></blockquote>
<p>Naturally you want to fix anything in your error log so I went looking for a solution.</p>
<p>In my case it turns out what was happening was in one of my .htaccess files I was giving a complete URL as the path to error documents, the fix was to change it to a relative path.</p>
<p>Which basically means I had something like;</p>
<pre>ErrorDocument 401 http://mysite.com/errorpage.html</pre>
<p>And I had to change it to</p>
<pre>ErrorDocument 401 /errorpage.html</pre>
<p>Unfortunately it doesn't tell you much about the location of your .htaccess file and if you have several sites on a server hunting it down could be a bummer.  I would suggest using <em>find</em> and <em>grep</em> commands to help narrow down your list of possibilities. I did something like this;</p>
<pre>find -name '.htaccess' -exec grep ErrorDocument {} \; -print</pre>
<p>From inside the home directory and it returned all the .htaccess files with reference to ErrorDocument.</p>
<p>A very quick fix but one that will keep my Error Log all the cleaner!</p>
