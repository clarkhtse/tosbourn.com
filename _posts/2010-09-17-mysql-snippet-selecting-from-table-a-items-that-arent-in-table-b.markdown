---
layout: post
status: publish
published: true
title: MySQL snippet - Selecting from table a items that aren't in table b.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 289
wordpress_url: http://www.tosbourn.com/?p=289
date: '2010-09-17 15:18:22 +0100'
date_gmt: '2010-09-17 14:18:22 +0100'
categories:
- Development Help
tags:
- MySQL
- code
comments:
- id: 147
  author: Me
  author_email: me@rlyness.co.uk
  author_url: ''
  date: '2012-06-22 13:30:00 +0100'
  date_gmt: '2012-06-22 12:30:00 +0100'
  content: |-
    i had to use something similar when coding a website. had to buy an SQL book to help teach myself this stuff:

    SELECT date_format(FROM_UNIXTIME(f.date),'%d-%m-%Y') AS date, GROUP_CONCAT(CONVERT(f.id, CHAR(3000)) ORDER BY f.date, f.id) AS ids, f.date AS unixdateFROM fixtures AS fWHERE f.date &gt; unix_timestamp()AND f.outcome = ''AND f.id NOT IN(SELECT r.fixtureIDFROM results AS rWHERE r.userID = '$_SESSION[userID]')GROUP BY date_format(FROM_UNIXTIME(f.date),'%d-%m-%Y')ORDER BY f.date;
- id: 148
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-06-22 14:07:00 +0100'
  date_gmt: '2012-06-22 13:07:00 +0100'
  content: Cheers for sharing that code.
---
<p>Today I needed to select something from a table on the condition that the ID of the row in the table did not appear in another table.</p>
<p>Initially I thought this was going to be slightly difficult to do, or at least a bit convoluted but it turned out to be really simple.</p>
<blockquote><p>SELECT table_a.id FROM table_a LEFT JOIN table_b ON table_a.id = table_b.aid WHERE table_b.aid IS NULL;</p></blockquote>
<p>Since you are using a LEFT JOIN table_b.aid can return NULL values, and these are the ones you are looking for.</p>
