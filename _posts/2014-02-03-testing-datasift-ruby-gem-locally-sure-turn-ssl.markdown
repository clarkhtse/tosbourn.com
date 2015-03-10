---
layout: post
status: publish
published: true
title: When testing the datasift ruby gem locally be sure to turn SSL off
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1839
wordpress_url: http://tosbourn.com/?p=1839
date: '2014-02-03 18:51:15 +0000'
date_gmt: '2014-02-03 17:51:15 +0000'
categories:
- Development Help
tags:
- Ruby
- SSL
- DataSift
comments: []
---
<p>I am getting to play with the awesome DataSift service as part of a project I am working on in Rumble and I was coming across some weird issues when testing locally, basically the consume would start but never actually get anywhere, it would create the connection but not fail or return anything, it would just sit there.</p>
<p>The fix that worked for me isn't something I would recommend in production, but for local testing I just turned off the need to use SSL for the user object.</p>
<p>So when I create my user like this;</p>
<pre><code>@user  = DataSift::User.new("#{username}", "#{api_key}")</code></pre>
<p>I then call the following;</p>
<pre><code>@user.enableSSL(false)</code></pre>
<p>Now when I do something like;</p>
<pre><code>@consumer = @user.getConsumer(DataSift::StreamConsumer::TYPE_HTTP, 'my_stream_hash')
@consumer.consume(true) do
    ...
end</code></pre>
<p>Everything works as expected :-)</p>
