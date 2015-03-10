---
layout: post
status: publish
published: true
title: MySQLslap - A quickstart guide
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1527
wordpress_url: http://tosbourn.com/?p=1527
date: '2013-05-21 13:49:47 +0100'
date_gmt: '2013-05-21 12:49:47 +0100'
categories:
- Development Help
tags:
- MySQL
- MySQLSlap
- Performance
comments:
- id: 293
  author: Drake
  author_email: eugene@greendrake.info
  author_url: ''
  date: '2013-12-02 21:45:00 +0000'
  date_gmt: '2013-12-02 20:45:00 +0000'
  content: |-
    &gt; because it is called create I wrongly assumed at the start it would kill my current database, it does not



    Beware - in case of using "--auto-generate-sql" flag the database WILL be killed.
- id: 295
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-05 13:21:00 +0000'
  date_gmt: '2013-12-05 12:21:00 +0000'
  content: Excellent addition, thanks Drake!
---
<p>Let me set the scene of how I stumbled upon the need for MySQLslap.</p>
<p>The database server was getting hit hard and slowing down the application, we narrowed the issue down to one potentially bad query.</p>
<p>We then took a copy of some production data, put it on our local machines and started hacking to see if the query could be improved.</p>
<p>Even though using <code>EXPLAIN</code> we were able to see it was a bad query, and running our new query through <code>EXPLAIN</code> made it look like a good query, we couldn't actually benchmark how much better it was. You see our issue was that when ran once the query finished in a reasonable amount of time, the issue only seemed to appear under production load.</p>
<p>There are plenty of tools available for testing your code under load, but I didn't want anything above these queries dirtying the results, for example I didn't want ActiveRecord to try and do anything smart with caching, I wanted only to see what SQL statement worked best.</p>
<p>Turns out MySQL comes with a tool to help you do just that, MySQLslap.</p>
<h2>MySQLslap</h2>
<p>As the name suggests MySQLslap slaps your MySQL tables with a load of queries at a rate and concurrency that you set.</p>
<p>After the queries have ran it will produce a small table breaking down the times for you, which allows you to easily compare and contrast.</p>
<p>Here is an example of some output from MySQLslap;</p>
<pre><code>
	Average number of seconds to run all queries: 0.014 seconds
	Minimum number of seconds to run all queries: 0.012 seconds
	Maximum number of seconds to run all queries: 0.017 seconds
	Number of clients running queries: 50
	Average number of queries per client: 2 
</code></pre>
<p>This was generated from one command, that took a very small amount of time to set up.</p>
<h2>MySQLslap - Setting it up</h2>
<p>In order to get the above output I just needed to enter one line into my terminal;</p>
<p><code>mysqlslap --concurrency=50 --iterations=5 --query=/Users/me/<wbr></wbr>Desktop/test1.sql --create-schema=my_database  -umy_username -pmy_password</code></p>
<p>I will go through each flag in turn;</p>
<ul>
<li><span style="line-height: 14px;"><strong>mysqlslap</strong> - This is the program we are running, if you don't have it installed make sure you are running at least MySQL 5.1.4</span></li>
<li><strong>--concurrency</strong> - This is how many connections you want to emulate  very roughly this adds more load onto MySQL, imagine 50 people hitting the same page at the same time.</li>
<li><strong>--iterations</strong> - This is how many times you want to run the test, obviously the more you do it the more accurate your average will be.</li>
<li><strong>--query</strong> - You can type the query or queries into here, but I preferred to have them saved in a .sql file, so in my case I just reference where my file is located (note: you cannot reference the home directory by typing <code>~/</code> mysql doesn't understand it)</li>
<li><strong>--create-schema</strong> - This is the most confusing flag in my opinion, this means which database you want the test to use, because it is called create I wrongly assumed at the start it would kill my current database, it does not (but any queries you run will affect it)</li>
<li><strong>-u</strong> - The username you use to connect to your database (optional depending on your setup)</li>
<li><strong>-p</strong> - The password you use to connect to your database (optional depending on your setup)</li>
</ul>
<p>Hopefully that will help get you on your way.</p>
<h2>MySQLslap resources</h2>
<p>Here are a collection of useful resources (I will add to this over time);</p>
<ul>
<li><a href="http://dev.mysql.com/doc/refman/5.1/en/mysqlslap.html"><span style="line-height: 1.714285714; font-size: 1rem;">MySQLslap from the MySQL docs</span></a></li>
</ul>
