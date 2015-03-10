---
layout: post
status: publish
published: true
title: Every time you write non-standard or invalid code
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1130
wordpress_url: http://tosbourn.com/?p=1130
date: '2012-10-23 23:36:35 +0100'
date_gmt: '2012-10-23 22:36:35 +0100'
categories:
- Development Help
tags:
- CSS
- html
- JavaScript
- Browsers
- Invalid
comments: []
---
<p><img src="http://tosbourn.com/wp-content/uploads/2012/10/invalid.png" alt="" title="invalid" width="622" height="236" class="alignright size-full wp-image-1132" /></p>
<p><span style="color:pink;">Warning — I am about to go on a rant.</span></p>
<p>Every time you write non-standard or invalid code and it works, just remember that some poor sonofabitch browser developer has had to spend developer time to interpret your shitty code, to work out that you probably meant to close that tag, or that you probably meant " when you used '. The same goes for when a crawler finds your content and spiders your website — if you haven't written your code correctly someone has had to write something to figure out your mess.</p>
<p>Before I get much further, full disclaimer — my code on this site doesn't <a href="http://validator.w3.org/check?uri=http%3A%2F%2Ftosbourn.com%2F&amp;charset=%28detect+automatically%29&amp;doctype=Inline&amp;group=0">validate</a>, I am indeed being part of the problem.</p>
<p>A good example of what I am talking about is how IE doesn't support &amp;apos; to many it feels like a bug on Microsoft's part, but it isn't because &amp;apos; isn't a supported HTML entity and they have no need to support it, but because so many people write their code with this in it in many people's eyes it is seen as a bug.</p>
<p>Now you may argue that the code had already been written, and the browser's job is to interpret websites and if a lot of websites do the same thing then the browser should be able to display that, and I guess that bares some weight, but here is the thing — imagine how good browsers could be if they didn't need to worry about incorrect code.</p>
<p>Imagine how much further specs could be if browser manufacturers were able to concentrate on new features and less on supporting shite code.</p>
<p>Interestingly, I can't find much written online about the amount of time or lines of code that are spent trying to support invalid code, I would love to hear from anyone who has access to that information.</p>
<p>Obviously if browsers were to stop supporting invalid code people would complain and ultimately stop using the browser, but what if all the major browsers got together and released something at the same time — sure it would break some of the web for a while, but the developers would soon get plenty of emails from people and plenty of grief until they fixed their mistake.</p>
<ul>
<li><a href="http://www.reddit.com/r/webdev/comments/11z0rc/think_about_this_every_time_you_write_nonstandard/">Reddit Link</a></li>
<li><a href="http://news.ycombinator.com/item?id=4690722">Hacker News Link</a></li>
</ul>
