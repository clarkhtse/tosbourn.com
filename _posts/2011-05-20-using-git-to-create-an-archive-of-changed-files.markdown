---
layout: post
status: publish
published: true
title: Using Git to create an archive of changed files.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 440
wordpress_url: http://tosbourn.com/?p=440
date: '2011-05-20 12:41:02 +0100'
date_gmt: '2011-05-20 11:41:02 +0100'
categories:
- Development Help
tags:
- Git
- Archive
comments:
- id: 284
  author: Dan
  author_email: dannjb@gmail.com
  author_url: ''
  date: '2013-11-19 15:25:00 +0000'
  date_gmt: '2013-11-19 14:25:00 +0000'
  content: Works almost perfectly, except for path names with spaces
- id: 287
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-11-20 20:47:00 +0000'
  date_gmt: '2013-11-20 19:47:00 +0000'
  content: That is interesting Dan, thanks for letting me know - that isn't something
    I have come across before as I try and always underscore any spaces.
- id: 370
  author: James
  author_email: rouzier@gmail.com
  author_url: ''
  date: '2014-01-14 17:43:00 +0000'
  date_gmt: '2014-01-14 16:43:00 +0000'
  content: |-
    You can try this command
    git diff -z --name-only HEAD^ | xargs -0 git archive -o update.zip HEAD
- id: 399
  author: JuanPablo AJ
  author_email: jpabloaj@gmail.com
  author_url: http://juanpabloaj.com/
  date: '2014-02-03 18:16:00 +0000'
  date_gmt: '2014-02-03 17:16:00 +0000'
  content: many thanks for the post, with this I can archive only the last modificated
    files.
- id: 404
  author: Sviatoslav Danylenko
  author_email: mybox@udf.su
  author_url: ''
  date: '2014-02-10 23:34:00 +0000'
  date_gmt: '2014-02-10 22:34:00 +0000'
  content: "try to use this one: \n\nzip update.zip $(git diff --name-only -D HEAD^)"
- id: 409
  author: Charl Mert
  author_email: charl.mert@gmail.com
  author_url: ''
  date: '2014-02-19 11:11:00 +0000'
  date_gmt: '2014-02-19 10:11:00 +0000'
  content: Thanks for this Toby, it's part of my deployment process now. oh and for
    paths with spaces you can escape them in bash&gt; git archive -o update.zip HEAD
    $(for file in $(git diff --name-only HEAD^); do printf "%qn" $file; done)
- id: 510
  author: Noobie
  author_email: noobie@gmai.com
  author_url: ''
  date: '2014-07-04 22:08:00 +0100'
  date_gmt: '2014-07-04 21:08:00 +0100'
  content: Note that you can also specify time e.g., <code>git diff --name-only HEAD@{"One
    week ago"}</code>
- id: 511
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-07-05 11:19:00 +0100'
  date_gmt: '2014-07-05 10:19:00 +0100'
  content: Nice!
- id: 640
  author: Ondra Medek
  author_email: xmedeko@gmail.com
  author_url: ''
  date: '2014-11-26 13:49:00 +0000'
  date_gmt: '2014-11-26 12:49:00 +0000'
  content: |-
    Thanks for your post, very usefull.
    IMHO ~ is better than ^ for the list of changed files:
    <code>git diff --name-only HEAD~</code>
    You may specify more commits, then
    <code>git diff --name-only HEAD~3</code>
---
<p>Often I have found myself in a situation where it would be really nice to have an archive of the files I have recently been working on.</p>
<p>Using two Git commands I can easily create such an archive.</p>
<p>The first actually creates the archive;</p>
<p><code>git archive -o update.zip HEAD</code></p>
<p>This will create an archive of the entire repository, which isn't what we want in this instance but is pretty handy to know.</p>
<p>The archive function accepts a list of files to archive, which is what we want to do and is where our second command comes in.</p>
<p><code>git diff --name-only HEAD^</code></p>
<p>This will do the commit before the head, which is what I want most of the time but this could be changed to get files between two commits or anything you wanted, check out the help section in git for the diff command.</p>
<p>Finally we want to bring this all together into one nice and easy command, thus;</p>
<p><code>git archive -o update.zip HEAD $(git diff --name-only HEAD^)</code></p>
<p>This wraps our second command with $(), this gets ran first and passes the result as a parameter into our first command.</p>
