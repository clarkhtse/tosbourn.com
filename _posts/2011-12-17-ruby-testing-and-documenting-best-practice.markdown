---
layout: post
status: publish
published: true
title: Ruby Testing and Documenting best practice
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 784
wordpress_url: http://tosbourn.com/?p=784
date: '2011-12-17 14:05:53 +0000'
date_gmt: '2011-12-17 13:05:53 +0000'
categories:
- Other
tags:
- Ruby
- Testing
- Documenting
comments: []
---
<p>So this morning I thought I would get stuck into my <a title="My Next Project – Stack Exchange Question Promoter using Ruby" href="http://tosbourn.com/2011/12/ruby-based-stack-exchange-question-promoter/my-next-project-stack-exchange-question-promoter-using-ruby/">little learning project</a>.</p>
<p>My first issue was that I wasn't 100% sure how I should be unit testing whatever I write or how I should be documenting it. Some digging around led me to a really useful article called <a href="http://www.caliban.org/ruby/rubyguide.shtml#tests">The Unofficial Ruby Guide</a>.  The article has documented some best practice, which I have tried to double check at various other websites and they seem to check out.</p>
<p>The testing functionality that comes built into Ruby seems to be fairly straight forward to use and robust enough for my small script - during my research I found <a href="http://evan.tiggerpalace.com/articles/2010/12/18/ruby-test-unit-sucks-and-why-i-still-use-it/">this article </a>discussing the relative pros and cons of it and I am happy enough that Ruby Test::Unit will do the job.</p>
<p>Documenting seems to be done by a great many people using <a href="http://rdoc.sourceforge.net/doc/index.html">RDoc</a>, again for what I need it to do for this script I see no reason why I shouldn't use it, the syntax seems relatively intuitive and it is built into Netbeans so I can create code documentation whenever I wish.</p>
