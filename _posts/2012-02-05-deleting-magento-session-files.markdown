---
layout: post
status: publish
published: true
title: Deleting Magento Session Files
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 831
wordpress_url: http://tosbourn.com/?p=831
date: '2012-02-05 17:16:12 +0000'
date_gmt: '2012-02-05 16:16:12 +0000'
categories:
- Development Help
tags:
- Magento
- Sessions
comments:
- id: 118
  author: professionele webshop
  author_email: maartenpeeters79@hotmail.com
  author_url: http://www.magentowebshop.nu/
  date: '2012-03-12 17:15:00 +0000'
  date_gmt: '2012-03-12 16:15:00 +0000'
  content: |-
    Hi Toby,

    Thanks for this nice info!
- id: 676
  author: Javier Villanueva
  author_email: javiervd@gmail.com
  author_url: http://www.jvsoftware.com/
  date: '2015-01-17 22:17:00 +0000'
  date_gmt: '2015-01-17 21:17:00 +0000'
  content: |-
    On a similar note if you ever need to delete sessions manually you can do something like:

    find /path/to/var/session -type f -cmin +$(/usr/lib/php5/maxlifetime) -delete



    That way you'll only delete files older than your maxlifetime setting.
- id: 677
  author: soifou
  author_email: fleur.fr@gmail.com
  author_url: ''
  date: '2015-01-18 10:15:00 +0000'
  date_gmt: '2015-01-18 09:15:00 +0000'
  content: "A little precision,\n\n\"when a linux box has ran out of space but reports
    that there is still some space left\" probably means  that your box ran out of
    *** inodes *** space. \n\nTo check it, you can report your file system disk space
    usage by doing a (-i is for inode) :\n$ df -i\n\n\n\n@Javier : thanks for this
    elegant command :)"
- id: 678
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-01-18 11:41:00 +0000'
  date_gmt: '2015-01-18 10:41:00 +0000'
  content: Thanks Soifou!
- id: 679
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-01-18 11:41:00 +0000'
  date_gmt: '2015-01-18 10:41:00 +0000'
  content: Thanks for sharing!
---
<p>Whilst being an excellent ecommerce platform, Magento isn't the tidiest of beasts and likes to leave session data lying around at its arse.</p>
<p>Session files are tiny so you could be forgiven for ignoring them most of the time, but the issue is there is a lot of them and Magento doesn't have a built in method for dealing with them.</p>
<p>Because they are so small but there is so much of them I have actually found times when a linux box has ran out of space but reports that there is still some space left, this I think is because the processes that calculate filesizes are falling over the sheer amount of session files left by Magento.</p>
<p>Up until recently I was incorrectly deleting the session files using a cronjob, but as was pointed out to me on <a href="http://www.reddit.com/r/Magento/comments/1736do/deleting_magento_session_files/">Reddit</a> this could have negative side effects for users of the site.</p>
<p>The correct way of handling this is to set up PHP to garbage collect, do this by adding the following to your php.ini file;</p>
<pre><code>; The probability is calculated by using gc_probability/gc_divisor,
; e.g. 1/100 means there is a 1% chance that the GC process starts
; on each request.

session.gc_probability = 1
session.gc_divisor = 100

; After this number of seconds, stored data will be seen as 'garbage' and
; cleaned up by the garbage collection process.
session.gc_maxlifetime = 1440</code></pre>
<p>What I was doing before is something like;</p>
<pre>find /path/to/magento/sessions/ -name "sess*" -type f -delete</pre>
<p>But as I say, this isn't the preferred way to handle it.</p>
