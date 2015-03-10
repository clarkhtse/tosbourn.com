---
layout: post
status: publish
published: true
title: Using Loops in Jasmine
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1560
wordpress_url: http://tosbourn.com/?p=1560
date: '2013-06-07 16:52:19 +0100'
date_gmt: '2013-06-07 15:52:19 +0100'
categories:
- Development Help
tags:
- JavaScript
- Testing
- Jasmine
comments:
- id: 285
  author: Kevin
  author_email: kevin@gravityworksdesign.com
  author_url: ''
  date: '2013-11-19 15:59:00 +0000'
  date_gmt: '2013-11-19 14:59:00 +0000'
  content: Thank you!  I couldn't figure out how to loop my Jasmine tests to be like
    NUnit's TestCase - you save me a ton of time.
- id: 331
  author: frosty84
  author_email: frosty84@gmail.com
  author_url: ''
  date: '2013-12-16 11:25:00 +0000'
  date_gmt: '2013-12-16 10:25:00 +0000'
  content: Thank you! You saved my day!
- id: 332
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-16 11:40:00 +0000'
  date_gmt: '2013-12-16 10:40:00 +0000'
  content: Happy to help!
- id: 333
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-16 11:40:00 +0000'
  date_gmt: '2013-12-16 10:40:00 +0000'
  content: No bother at all Kevin, happy to help!
- id: 562
  author: gaurav
  author_email: gaurav_bcs10@nitc.ac.in
  author_url: ''
  date: '2014-08-21 07:34:00 +0100'
  date_gmt: '2014-08-21 06:34:00 +0100'
  content: |-
    dude you just saved my full day.
    Thanks buddy
- id: 563
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-08-21 09:50:00 +0100'
  date_gmt: '2014-08-21 08:50:00 +0100'
  content: You are more than welcome :-)
- id: 631
  author: Rodrigo
  author_email: restebanez@mdsol.com
  author_url: ''
  date: '2014-11-03 18:16:00 +0000'
  date_gmt: '2014-11-03 17:16:00 +0000'
  content: Thank you very much! If it doesn't work, change input.size for input.length
- id: 639
  author: senatori
  author_email: myshawshankredemption@gmail.com
  author_url: ''
  date: '2014-11-21 18:47:00 +0000'
  date_gmt: '2014-11-21 17:47:00 +0000'
  content: Thanks! Saved me a bit of pain!
- id: 673
  author: Stephen
  author_email: twitter@chumster.net
  author_url: ''
  date: '2015-01-12 04:23:00 +0000'
  date_gmt: '2015-01-12 03:23:00 +0000'
  content: Thanks man...saved me some time..
---
<p>If you want to test your code against 10 different inputs you don't want to have to write 10 different tests. You want to write one test you can call 10 times.</p>
<p>The cleanest way to achieve this is to have your inputs and outputs stored in an array or object (In the example below I have chosen an array).</p>
<p>Intuitively (especially if you are familiar with how to write Rspec tests) it might feel like all you need to do is wrap your <code>it</code> block in a for loop and have your arrays feed into it, unfortunately due to the nature of how Jasmine executes this will not work.</p>
<p>What you need to do is wrap your <code>it</code> block inside a function, which you can then call from inside a loop. For example;</p>
<pre><code>describe('this is my looping test!', function() {
  var input = [1,2,3];
  var output = [10, 20, 30];

  function test_my_times_ten(input, output) {
    it('should multiply ' + input + ' by 10 to give ' + output, function() {
      expect(input * 10).toEqual(output)
    });
  }

  for(var x = 0; x &lt; input.size; x++) {
    test_my_times_ten(input[x], output[x]);
  }
});</code></pre>
<p>With this technique you can see how you could quickly build up a very large and comprehensive test suite without writing a large amount of tests, things start to get really interesting if you start having nested loops passing in input. Just be aware of the performance implications of nested loops though!</p>
