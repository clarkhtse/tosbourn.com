---
layout: post
status: publish
published: true
title: Using Ember's App.reset() to kill off any local data
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2065
wordpress_url: http://tosbourn.com/?p=2065
date: '2014-06-23 17:41:06 +0100'
date_gmt: '2014-06-23 16:41:06 +0100'
categories:
- Development Help
tags:
- Ember
comments: []
---
<p>Recently I stumbled across an issue that when my user had logged out of an Ember app and a new user had logged in, sometimes some data was persisting at the front end.</p>
<p>The API was built correctly so the new user couldn't interact with any of it, but it was still messy and a bad experience for the user.</p>
<p>I started looking for a good way to clear out all of this information. I wanted something that ideally I could call once and it would apply to all models.</p>
<p>Happily there is App.reset()</p>
<p><a href="http://emberjs.com/api/classes/Ember.Application.html#method_reset">The documentation</a> says it is normally only used in tests but I think this it suits our needs perfectly here.</p>
<p>This is the order things happen in once you call App.reset()</p>
<ol>
<li>Deactivate existing routes</li>
<li>Destroy all objects in the container</li>
<li>Create a new application container</li>
<li>Re-route to the existing url</li>
</ol>
<p>Because of the note that it is normally only used in test I would be interested to know if there is a better way I should be doing it?</p>
