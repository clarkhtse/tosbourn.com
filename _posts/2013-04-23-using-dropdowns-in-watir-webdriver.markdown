---
layout: post
status: publish
published: true
title: Using Dropdowns in Watir Webdriver
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1462
wordpress_url: http://tosbourn.com/?p=1462
date: '2013-04-23 09:51:29 +0100'
date_gmt: '2013-04-23 08:51:29 +0100'
categories:
- Development Help
tags:
- Testing
- Watir
- Watir Webdriver
- Select Boxes
comments: []
---
<p>I had been having some issues getting a dropdown to select a value using the Watir Webdriver and I wanted to briefly write up what I was doing verses what I should have been doing.</p>
<p>In my specific case I wanted to use Watir to drive a date selection using the jQuery datepicker so I inspected the elements and found a class I could latch onto to grab the year dropdown.</p>
<pre><code>select(:class, 'ui-datepicker-year').select('2006')</code></pre>
<p>I thought this would work, but it was telling me that instead of a symbol it was expecting an array. I am guessing this is because out of context it doesn't know if I mean a select element or I want to select something.</p>
<p>The fix was to chain my select with a parent element, like so:</p>
<pre><code>div(:class, 'ui-datepicker-title').select(:class, 'ui-datepicker-year').select('2006')</code></pre>
<p>Now Watir knows that <code>.select</code> means a select box and not to select something.</p>
<p>If you are interested in finding out more I have written up a short blog post about <a title="Controlling a jQuery datepicker with Watir" href="http://tosbourn.com/2013/04/watir/controlling-a-jquery-datepicker-with-watir/">controlling the jQuery datepicker in Watir</a>.</p>
