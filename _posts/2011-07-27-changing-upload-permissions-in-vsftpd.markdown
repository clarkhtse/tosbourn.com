---
layout: post
status: publish
published: true
title: Changing upload permissions in vsftpd
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 481
wordpress_url: http://tosbourn.com/?p=481
date: '2011-07-27 09:39:00 +0100'
date_gmt: '2011-07-27 08:39:00 +0100'
categories:
- Development Help
tags:
- FTP
- vsftpd
comments:
- id: 98
  author: Nathan Sorensen
  author_email: ndsorensen@gmail.com
  author_url: ''
  date: '2012-01-01 00:18:00 +0000'
  date_gmt: '2011-12-31 23:18:00 +0000'
  content: This post just saved me from so much headache!  Thank you!!
- id: 99
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-01-01 12:32:00 +0000'
  date_gmt: '2012-01-01 11:32:00 +0000'
  content: Glad it worked for somebody else too!
- id: 132
  author: Jacob Valenta
  author_email: jacob.valenta@gmail.com
  author_url: http://profiles.google.com/jacob.valenta
  date: '2012-04-20 00:43:00 +0100'
  date_gmt: '2012-04-19 23:43:00 +0100'
  content: Thank you!
- id: 160
  author: sok
  author_email: sok@interzet.ru
  author_url: ''
  date: '2013-06-08 16:13:00 +0100'
  date_gmt: '2013-06-08 15:13:00 +0100'
  content: cool!
- id: 163
  author: Alo
  author_email: alo@alo.com
  author_url: ''
  date: '2013-06-10 13:31:00 +0100'
  date_gmt: '2013-06-10 12:31:00 +0100'
  content: Thanks dear
- id: 164
  author: Alo
  author_email: alo@alo.com
  author_url: ''
  date: '2013-06-10 13:31:00 +0100'
  date_gmt: '2013-06-10 12:31:00 +0100'
  content: Thanks dear
- id: 204
  author: Catalin
  author_email: catalinjora@yahoo.com
  author_url: ''
  date: '2013-08-22 10:47:00 +0100'
  date_gmt: '2013-08-22 09:47:00 +0100'
  content: Thanks man, I was struggling with this for a few hours.
- id: 256
  author: RevoLand
  author_email: revoland@windowslive.com
  author_url: ''
  date: '2013-10-30 01:05:00 +0000'
  date_gmt: '2013-10-30 00:05:00 +0000'
  content: You saved my life, thanks!
- id: 274
  author: Edward
  author_email: egsmwa@hotmail.com
  author_url: ''
  date: '2013-11-09 12:21:00 +0000'
  date_gmt: '2013-11-09 11:21:00 +0000'
  content: Thanks you saved my day.
- id: 296
  author: Fernando
  author_email: n@ndo.im
  author_url: ''
  date: '2013-12-05 14:15:00 +0000'
  date_gmt: '2013-12-05 13:15:00 +0000'
  content: |-
    In my case it  didn't solve my problem.


    I'm using anonymous login, so I had to add one more line to the conf file:


    anon_umask=022



    Cheers!
- id: 627
  author: Petes
  author_email: petes@sapo.pt
  author_url: ''
  date: '2014-10-22 17:22:00 +0100'
  date_gmt: '2014-10-22 16:22:00 +0100'
  content: |-
    If you user

    local_umask=000
    file_open_mode=0755


    then the final mask will me determined by file_open_mode
---
<p>Recently I had to change the permissions for files that were uploaded for the local user via FTP.  I wanted them to be 755.</p>
<p>Initially I thought it would be as simple as changing the vsftpd.conf file to set the local_umask=0755 but this change alone did nothing.  After a lot of googling and reading I came across this optimal solution, which I present here to hopefully save others some time.</p>
<p>local_umask=002<br />
chmod_enable=YES<br />
file_open_mode=0755</p>
