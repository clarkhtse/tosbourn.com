---
layout: post
status: publish
published: true
title: Ruby Fizz Buzz Solution
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 798
wordpress_url: http://tosbourn.com/?p=798
date: '2012-01-12 00:42:07 +0000'
date_gmt: '2012-01-11 23:42:07 +0000'
categories:
- Other
tags:
- Ruby
- Fizz Buzz
comments:
- id: 482
  author: Jordan Poulton
  author_email: jordan@oxfordentrepreneurs.co.uk
  author_url: ''
  date: '2014-05-16 17:41:00 +0100'
  date_gmt: '2014-05-16 16:41:00 +0100'
  content: |-
    Hey Toby - I thought I'd share this version I made using Ruby and RSpec :)

    http://youtu.be/CHTep2zQVAc
- id: 484
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-05-17 22:12:00 +0100'
  date_gmt: '2014-05-17 21:12:00 +0100'
  content: Lovely stuff Jordan!
---
<p>I decided as part of my wanted to get to know Ruby a bit better I would go back to basics and try out some of the programming challenges that people new to programming are normally asked to try out.</p>
<p>For those that don't know, Fizz Buzz is a children's game where you count upwards from 1, each time the number is divisible by 3 they have to shout Fizz, each time it is divisible by 5 they have to shout Buzz and each time it is divisible by both 3 and 5 they have to shout 'FizzBuzz'.</p>
<p>Obviously this is a trivial task for a seasoned programmer, but it is a nice example to get used to the syntax of a new language.</p>
<p>This was my first attempt - pretty boring and self-explanatory;</p>
<pre>for i in (1..20)	
    x = ''
    x += "Fizz" if (i % 3 == 0) 
    x += "Buzz" if (i % 5 == 0)
    puts(x.empty? ? i : x)
end</pre>
<p>My thinking was that I wanted to keep my puts to a minimum and maintain readability, I think this does just that.</p>
<p>Once I completed the task I started looking around for more creative solutions and stumbled on <a href="http://fizzbuzz.rubyforge.org/svn/trunk/lib/fizzbuzz.rb" target="_blank">this code</a>;</p>
<p>Some of the solutions are just awesome - fizzbuzz_sequence7_reverse especially wins it for me and I think if ever I need to show anyone Fizz Buzz I will think up more of the 'exotic' ways of doing it like these guys did.</p>
