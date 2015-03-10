---
layout: post
status: publish
published: true
title: CouchRest Rails Setup - Setting a blank username/password is not the same as
  not setting a username/password
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1847
wordpress_url: http://tosbourn.com/?p=1847
date: '2014-02-10 13:38:50 +0000'
date_gmt: '2014-02-10 12:38:50 +0000'
categories:
- Development Help
tags:
- Ruby on Rails
- CouchDB
- CouchRest
- Credentials
comments: []
---
<p>If you are using CouchRest in your Rails project and locally you don't want to set a username and password for your couchdb install then bare in mind that the following are not the same;</p>
<pre><code>CouchRest::Model::Base.configure do |config|
    config.connection = {
        :protocol =&gt; 'http',
        :host     =&gt; '127.0.0.1',
        :port     =&gt; 5984,
        :prefix   =&gt; '',
        :suffix   =&gt; Rails.env,
        :join     =&gt; '_'
    }
  end</code></pre>
<p>The code above has no username and password set, so it will not try and speak to CouchDB with any credentials.</p>
<p>The code below *has* a username and password set but they are both blank, so it will try and speak to CouchDB with the username and password both being set to an empty string, this will result in a 401 Not authorised error.</p>
<pre><code>CouchRest::Model::Base.configure do |config|
    config.connection = {
        :protocol =&gt; 'http',
        :host     =&gt; '127.0.0.1',
        :port     =&gt; 5984,
        :prefix   =&gt; '',
        :suffix   =&gt; Rails.env,
        :join     =&gt; '_',
        :username =&gt; '',
        :password =&gt; ''
    }
  end</code></pre>
<p>This isn't particularly unique to CouchRest at all but it tripped me up earlier so I figured I would share :-)</p>
