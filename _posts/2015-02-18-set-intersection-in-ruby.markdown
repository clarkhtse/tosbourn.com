---
layout: post
status: publish
published: true
title: Set Intersection in Ruby
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2583
wordpress_url: http://tosbourn.com/?p=2583
date: '2015-02-18 23:49:37 +0000'
date_gmt: '2015-02-18 22:49:37 +0000'
categories:
- Development Help
tags:
- Ruby
- Set Intersection
comments:
- id: 693
  author: juanfatas
  author_email: katehuang0320@gmail.com
  author_url: ''
  date: '2015-02-20 05:05:00 +0000'
  date_gmt: '2015-02-20 04:05:00 +0000'
  content: |-
    Array#&amp; is way faster than Set operations.

    https://gist.github.com/JuanitoFatas/aa802614a2417d9edb50
- id: 694
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-02-20 09:27:00 +0000'
  date_gmt: '2015-02-20 08:27:00 +0000'
  content: |-
    Hey Juanfatas,

    Thanks for the comment, that is really interesting – I worry you are benchmarking more than you think, those "slower" methods are also having to load in "set" and do the setup of the object (the array method didn't do this, it already had the object made).

    I did some playing https://gist.github.com/tosbourn/c9aacfbd335f15d74453

    Interestingly it didn't effect the overall results, Arrays are still faster (good to know!) but they are now only 5x faster based on the sample data.

    With larger datasets I feel this could be closer, especially if you were to factor in the fact Arrays need to deal with uniqueness.
- id: 695
  author: Fahim Babar Patel
  author_email: pafahim@gmail.com
  author_url: http://in.linkedin.com/in/fahimbabarpatel/
  date: '2015-02-22 05:14:00 +0000'
  date_gmt: '2015-02-22 04:14:00 +0000'
  content: '+1'
- id: 696
  author: Mikhail Pobolovets
  author_email: styx.mp@gmail.com
  author_url: ''
  date: '2015-02-23 18:00:00 +0000'
  date_gmt: '2015-02-23 17:00:00 +0000'
  content: |-
    Yep, it is slower but not x13 times. Your code is not a good test. require "set" and Set.new(X) all the time tests more than intersection.

    Your test should look something like this:

    https://gist.github.com/styx/3d8a23250d899a53791f
---
<p>Let's talk about Set Intersection in Ruby.</p>
<p>There are times when you have two or more groups of data and you want to know what is common between them. When this happens it is good to know about set intersection.</p>
<h2>Set Intersection</h2>
<p>The intersection is the join in two sets of data where data belongs to both sets. It is easiest to describe with a diagram.</p>
<p><a href="http://tosbourn.com/wp-content/uploads/2015/02/Screen-Shot-2015-02-18-at-22.05.59.png"><img class="aligncenter wp-image-2584 size-large" src="http://tosbourn.com/wp-content/uploads/2015/02/Screen-Shot-2015-02-18-at-22.05.59-1024x702.png" alt="Venn diagram to describe intersection of sets" width="474" height="325" /></a></p>
<p>The mathematic notion for intersections is ∩. So if you wanted to write the intersection of A and B you would write A ∩ B.</p>
<h2>Set Intersection in Ruby</h2>
<p>There are a couple of ways you can do intersections in Ruby, I will talk you through both of them. The syntax is similar in both, so don't worry about having to learn lots of different things.</p>
<h2>Set Intersection with Arrays in Ruby</h2>
<p>I will cover arrays first because this is one of the most common objects found in Ruby code.</p>
<p>The syntax is <code>array &amp; array</code>, so much like we had A ∩ B we would do <code>A &amp; B</code></p>
<p>A working example;</p>
<p><code>[1, 1, 5, 5] &amp; [1, 2, 5] #=&gt; [ 1, 5 ]</code></p>
<p>When we do an intersection the array gets treated like a set and in a set everything should be unique. So if we changed the second array to include another 1 we would still get the same result;</p>
<p><code>[1, 1, 5, 5] &amp; [1, 1, 2, 5] #=&gt; [ 1, 5 ]</code></p>
<p>The intersection is not destructive, it doesn't change any arrays it creates a new one.</p>
<p>You can chain intersections together if you want to compare more than two arrays;</p>
<p><code>[1, 1, 5, 5] &amp; [1, 1, 2, 5] &amp; [5] #=&gt; [ 5 ]</code></p>
<p>The ordering of the final array is dictated by the order of the first array, so if we change our first example so that the 5's come first we would get;</p>
<p><code>[5, 5, 1, 1] &amp; [1, 2, 5] #=&gt; [ 5, 1 ]</code></p>
<p>This is good to know because there is no point in sorting all the arrays before performing an intersection.</p>
<p>The final thing to say about intersection is it is performant. Under the hood it compares the elements using <code>eql?</code> with their hash value (not to be confused with a hash object)</p>
<h2>Set Intersection with Sets in Ruby</h2>
<p>If you are treating your array like a set then maybe it should be a set?</p>
<p>Access to the Set object is just a require away. It acts like a hybrid between the usability of arrays and the speed gains with hashes.</p>
<p>To do the basic intersection with a set in ruby you would do something like;</p>
<pre><code>require "set"
x = Set.new([1,2,3])
y = Set.new([1,2])
x &amp; y #=&gt; #&lt;Set: {1, 2}&gt;</code></pre>
<p>Set also gives you access to a more friendly looking <code>intersection</code> method so we could have written our final line like;</p>
<p><code>x.intersection y #=&gt; #&lt;Set: {1, 2}&gt;</code></p>
<p>Which arguably expresses intent a bit more.</p>
