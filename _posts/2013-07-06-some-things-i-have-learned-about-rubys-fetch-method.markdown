---
layout: post
status: publish
published: true
title: Some things I have learned about Ruby's fetch method
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1585
wordpress_url: http://tosbourn.com/?p=1585
date: '2013-07-06 17:24:26 +0100'
date_gmt: '2013-07-06 16:24:26 +0100'
categories:
- Development Help
tags:
- Ruby
- Fetch
comments:
- id: 183
  author: icantbecool
  author_email: jordanstaub@gmail.com
  author_url: ''
  date: '2013-07-12 12:53:00 +0100'
  date_gmt: '2013-07-12 11:53:00 +0100'
  content: Great little informative post.
- id: 184
  author: Ignacio Piantanida
  author_email: napoplate@gmail.com
  author_url: ''
  date: '2013-07-14 06:32:00 +0100'
  date_gmt: '2013-07-14 05:32:00 +0100'
  content: "Also, <a href=\"http://www.ruby-doc.org/core-2.0/Hash.html#method-c-new\"
    rel=\"nofollow\">Hash#new</a> accepts either an object or a block as a parameter
    to return a default value.\n<code>\ntest = Hash.new{|h,k| \"Default_#{k}\"}\ntest[3]
    #=&gt; 'Default_3' \ntest[5] #=&gt; 'Default_5'\n</code>"
- id: 185
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-07-16 10:55:00 +0100'
  date_gmt: '2013-07-16 09:55:00 +0100'
  content: |-
    Thanks for sharing - I could see benefits of this when you have full control of the hash, but I personally don't like the idea of giving the hash a default value, simply because hashes shouldn't care if their keys are nil or if their keys exist.

    That is just my person preference though!
- id: 186
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-07-16 10:55:00 +0100'
  date_gmt: '2013-07-16 09:55:00 +0100'
  content: Thanks!
---
<p>Recently I have learned a couple of things about Ruby's fetch method that I would like to share.</p>
<p>The first is a pretty straightforward one, using fetch is preferable to using the ['key'] notation in times when you want your system to fall over if the key doesn't exist. Here is an example;</p>
<pre><code>test = {:a =&gt; 'test', :b =&gt; 'test'}

p test[:a]       #=&gt; 'test'
p test.fetch(:a) #=&gt; 'test'</code></pre>
<p>Nothing odd here, but what about;</p>
<pre><code>p test[:c]       #=&gt; nil (this could be dangerous)
p test.fetch(:c) #=&gt; `fetch': key not found (IndexError) Much safer if we aren't expecting nil</code></pre>
<p>The next thing I have learned is that if you have the case were you want default values to be added in the case of fetch not working, or indeed you want some better form of logging without the site falling over you can pass a block to fetch;</p>
<pre><code>p test.fetch(:c) { 'Default' } #=&gt; 'Default'</code></pre>
<p>Finally, you can pass a second parameter into fetch that would act as the default value, but this should be avoided because the second parameter is always evaluated, even if it isn't needed, so if you pass a method in there it is going to be called each time even though the return value may never be used.</p>
