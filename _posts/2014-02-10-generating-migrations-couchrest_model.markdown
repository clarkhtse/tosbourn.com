---
layout: post
status: publish
published: true
title: Generating migrations with couchrest_model
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1849
wordpress_url: http://tosbourn.com/?p=1849
date: '2014-02-10 13:55:09 +0000'
date_gmt: '2014-02-10 12:55:09 +0000'
categories:
- Development Help
tags:
- Ruby on Rails
- CouchRest_Model
- Migrations
comments: []
---
<p>CouchRest_Model is a lovely way to handle CouchDB calls from without your rails app, it provides an Active Record like interface to your data.</p>
<p>In a project I am working on at the moment I am using both CouchRest_Model and Active Record at the same time, which isn't a problem at all and they normally don't stand on each others feet.</p>
<p>I say normally because one time when it can cause issue is whenever you are generating migrations using the command <code>rails generate migration myMigration</code>.</p>
<p>You may find that if you run this you will get the following error;</p>
<pre><code>error  couchrest_model [not found]</code></pre>
<p>This is because CouchRest_Model assumes it is the default ORM, which is fine in the app, but not find for migration generation.</p>
<p>To get around this we can add a flag to our migration command;</p>
<pre><code>rails generate migration myMigration --orm=active_record</code></pre>
<p>This will allow the migration to generate as expected.</p>
