---
layout: post
status: publish
published: true
title: Controlling a jQuery datepicker with Watir
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1465
wordpress_url: http://tosbourn.com/?p=1465
date: '2013-04-23 10:17:49 +0100'
date_gmt: '2013-04-23 09:17:49 +0100'
categories:
- Development Help
tags:
- jQuery
- Ruby
- Watir
- Watir Webdriver
- Datepicker
comments:
- id: 279
  author: allen roulston
  author_email: aroulston@nuvoshift.com
  author_url: ''
  date: '2013-11-13 19:59:00 +0000'
  date_gmt: '2013-11-13 18:59:00 +0000'
  content: Hello, are you still working with WATIR?  I'm presently attempting to solve
    a datepicker automation puzzle.
- id: 280
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-11-13 20:21:00 +0000'
  date_gmt: '2013-11-13 19:21:00 +0000'
  content: |-
    Hey Allen,

    I still do a bit of work with Watir, but I haven't looked at it in a month or two.

    What is the issue you are having? Is there any code samples online anywhere?
---
<p>In my <a title="Using Dropdowns in Watir Webdriver" href="http://tosbourn.com/2013/04/watir/using-dropdowns-in-watir-webdriver/">last post</a> I talked about some issues using a dropdown with Watir, the context I was using that in was to complete a jQuery datepicker field that contained both a year and month dropdown.</p>
<p>In case anyone needs the code to be able to do this with Watir Webdriver here it is;</p>
<pre><code>@title = div(:class, 'ui-datepicker-title')
text_field(:class, 'datepicker').click
@title.select(:class, 'ui-datepicker-year').select_value('2006')
@title.select(:class, 'ui-datepicker-month').select('Jan')
table(:class, 'ui-datepicker-calendar').a(:class, 'ui-state-default').click</code></pre>
<p><code>@title</code> is just a container for the <code>div</code> that contains it.</p>
<p>The two lines with <code>.select</code> will change the value of the year and month dropdowns, there is an change event associated with these inside of jQuery so it will update the calendar automatically for you.</p>
<p>The final line is a bit of a hack because each day doesn't have a unique id or class, in my test I didn't really care about the day so I just picked the first standard weekday but you could use <code>:index, 5</code> or something with the <code>a</code> function and play about to pick the appropriate day.</p>
