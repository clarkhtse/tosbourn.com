---
layout: post
status: publish
published: true
title: A case for writing unit tests for your blog posts
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1803
wordpress_url: http://tosbourn.com/?p=1803
date: '2013-12-29 11:25:34 +0000'
date_gmt: '2013-12-29 10:25:34 +0000'
categories:
- Other
tags:
- Testing
- Writing
- Editing
comments:
- id: 351
  author: John Jelinek IV
  author_email: john@johnjelinek.com
  author_url: ''
  date: '2013-12-29 19:15:00 +0000'
  date_gmt: '2013-12-29 18:15:00 +0000'
  content: This is ok, but if you don't have an automated test runner, it's pretty
    useless.
- id: 352
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-29 22:09:00 +0000'
  date_gmt: '2013-12-29 21:09:00 +0000'
  content: Haha - That would be a very high level DSL you would need!
- id: 353
  author: dima
  author_email: dima@ceata.org
  author_url: ''
  date: '2013-12-30 02:59:00 +0000'
  date_gmt: '2013-12-30 01:59:00 +0000'
  content: like Cucumber?
- id: 354
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-30 08:49:00 +0000'
  date_gmt: '2013-12-30 07:49:00 +0000'
  content: Exactly, only for plain English blog posts!
- id: 355
  author: Karlo
  author_email: karlo.smid@gmail.com
  author_url: ''
  date: '2013-12-30 10:24:00 +0000'
  date_gmt: '2013-12-30 09:24:00 +0000'
  content: 'Answering five W''s is also good technique: what, when, why, who, where.
    http://www.education.com/study-help/article/brainstorming-techniques-5-mapping/'
- id: 356
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-30 10:26:00 +0000'
  date_gmt: '2013-12-30 09:26:00 +0000'
  content: Thanks for posting Karlo, that makes a lot of sense :-)
- id: 357
  author: Miguel de Luis
  author_email: luis.miguelde@gmail.com
  author_url: http://sabiavida.com/
  date: '2013-12-31 12:13:00 +0000'
  date_gmt: '2013-12-31 11:13:00 +0000'
  content: Actually, that's not a bad idea at all. It makes me remember of a very
    old technique where you first wrote a summary of the article and then expanded
    it.
---
<p>Just thinking out loud here; the way I normally write posts (this one included) is I have a rough idea of what I want to say and I normally just start saying it, I might write a few key sentences or paragraphs and then work out ways to join them together.</p>
<p>This is a very quick process, it can also lead to posts that are longer than they need to be and potentially ones that veer off topic.</p>
<p>For some posts it isn’t a problem (like, I feel, this one) I quite like a conversational post that has the impression of being only slightly planned.</p>
<p>For other posts it might be beneficial to purposely keep them succinct, for example if I find installing a certain plugin wasn’t as straight forward as I would have liked, or my particular setup meant I had to jump through some hoops in a slightly different order to what the README file would suggest.</p>
<p>In these cases I would suggest perhaps we need to treat the post more like a body of code and write some unit tests for it, here is an example of what a post unit test might look like.</p>
<ul>
<li>The post should describe the error message you might initially see.</li>
<li>The post should describe the steps to rectify the error message.</li>
<li>The post should describe what should be done if the error message persists.</li>
<li>The post should contain a screen shot of the file you need to click on.</li>
</ul>
<p>Now we have this the challenge becomes how to get these ‘tests’ passing with as few words as possible (just like coding, we want to go green as soon as possible!)</p>
<p>Once we are happy our post completes the goals, it is time to refactor! We might find a slightly different order would work well, or maybe the terminology isn’t technical enough (or is too technical), we might even find a couple of introductory paragraphs would really work well. Just remember after every edit we should check the test spec we have written to make sure everything is still passing.</p>
<p>I am going to try this out on the next post I want to write that I feel would benefit from being slightly less conversational in tone - I will let you know how I get on and would love it if you could share any thoughts.</p>
