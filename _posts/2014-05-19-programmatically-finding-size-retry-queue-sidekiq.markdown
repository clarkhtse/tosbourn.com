---
layout: post
status: publish
published: true
title: Programmatically finding out the size of the retry queue with Sidekiq
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1900
wordpress_url: http://tosbourn.com/?p=1900
date: '2014-05-19 11:00:58 +0100'
date_gmt: '2014-05-19 10:00:58 +0100'
categories:
- Development Help
tags:
- Sidekiq
comments: []
---
<p>There is an API that Sidekiq provies for programmatically querying the state of the various queues under Sidekiq's control.</p>
<p>If you don't want to expose the web interface to the world then using this API is a must.</p>
<p>Here is some sample code for finding how many items are currently in the retry queue, if you have too many jobs constantly failing there is likely something you need to change in your worker.</p>
<pre><code>retry_queue = Sidekiq::RetrySet.new
retry_queue.size</code></pre>
<p>I would encourage you to read more about the <a href="https://github.com/mperham/sidekiq/wiki/API">API</a>.</p>
