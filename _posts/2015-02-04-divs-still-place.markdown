---
layout: post
status: publish
published: true
title: Divs still have their place
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2528
wordpress_url: http://tosbourn.com/?p=2528
date: '2015-02-04 21:52:37 +0000'
date_gmt: '2015-02-04 20:52:37 +0000'
categories:
- Development Help
tags:
- Semantics
- '365'
comments: []
---
<h2>Or – Don’t use semantics wrong.</h2>
<p>HTML5 is a wonderful thing, it has provided us with elements that really help to describe the content that resides within them.</p>
<p>When HTML5 started to become widely adopted and accepted as the standard for production ready web projects there was a big push from the community to get people to think about some of these new elements and to use them in place of  <code>&lt;div&gt;</code>s.</p>
<p>A good example of this is <code>&lt;aside&gt;</code>. I have seen people getting virtually crucified for using a <code>&lt;div&gt;</code> when an <code>&lt;aside&gt;</code> does a much better job of explaining that some particular content is supplementary information.</p>
<h2>Tables</h2>
<p>It reminded me of the time we moved from table based layouts to CSS based ones – people rightly rose up in arms when they saw someone incorrectly use a <code>&lt;table&gt;</code> when a <code>&lt;div&gt;</code> would do.</p>
<p>One of the issues is that we were shouting that tables are bad, not that semantics are good. The downside of this is that a lot of people just stopped using tables altogether.</p>
<p>Tables are great for displaying tabular information – and there is a lot of tabular information on the web today that is incorrectly marked up using <code>&lt;div&gt;</code>s and <code>&lt;span&gt;</code>s because people are too scared to consider <code>&lt;table&gt;</code> anymore.</p>
<h2>Consider the Div</h2>
<p>So what does all this have to do with <code>&lt;div&gt;</code>s still having their place?</p>
<p>A common theme I have started to see in web design over the past year or so is people using elements like <code>&lt;section&gt;</code>, <code>&lt;header&gt;</code> and <code>&lt;aside&gt;</code> incorrectly.</p>
<p>What appears to be happening is people have had it beaten into them that these new elements are better and <code>&lt;divs&gt;</code> are bad. The correct message is that you should consider the semantics of your markup. So we see the same thing as we got after the move away from table based layouts – people avoiding the old elements altogether.</p>
<h2>The problems with just replacing Divs</h2>
<p>You might wonder why this is a problem – at the end of the day they are all block level elements without their own browser based styling so the end user won't see any difference.</p>
<p>The problem is that all these other elements have a semantic meaning and even though they look the same in the browser, machines reading your code aren't smart enough to know that you didn't actually mean the content in an area represents a complete <code>&lt;article&gt;</code>.</p>
<p>The other problem is that by having no semantic information associated with them, in a strange way <code>&lt;div&gt;</code>s do have a meaning, which is to say this is just an arbitrary group of stuff. In other words – there is nothing to interpret here, move on!</p>
<h2>If there is one take away</h2>
<p>Please don't worry about following the latest development trends more than you worry about semantics.</p>
<p>Someone who has considered intent and made an educated choice is way further down the path to making great sites than someone who has read a load of articles on why table based layouts were the devil.</p>
