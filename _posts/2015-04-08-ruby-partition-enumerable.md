---
layout: post
status: publish
published: true
title: Ruby’s Partition for Enumerables
categories:
- Developer Help
tags:
- Ruby
---

Today I was on the Ruby freenode IRC room when I came across an example of
partitioning on enumerables I had never seen before and I wanted to share it.

Thanks to the user **eam** for bringing my attention to it.

## What does Enumerable#partition do?

When you use `partition` on something that is classed as an enumerable (for
example an array) each element will be asked a question, if true it will be
appended two one array, if false another. The end result is an array which
contains two arrays, one being values that responded to true, one that responded
to false.

Confused? This example will clear things up;

    (1..10).partition {|e| e.even? }
    => [[2, 4, 6, 8, 10], [1, 3, 5, 7, 9]]

Here we pass in the range 1 to 10 (which is an enumerable) and ask each element
if it is even. The elements which are even go into the first array, the elements
  which are odd are in the second.

We can build out this example really quickly my making partition actually set
something;

    even, odd = (1..10).partition {|e| e.even? }
    even
    => [2, 4, 6, 8, 10]
    odd
    => [1, 3, 5, 7, 9]

## Why would we use Enumerable#partition?

Our examples so far have come pretty much straight from [the
docs](http://ruby-doc.org/core-2.2.1/Enumerable.html#method-i-partition).

The majority of developers know what the even and odd numbers are between 1
 and 10, so we might want to look for something a bit more interesting to do.

What if we wanted to split up a large group of test results into those that have
passed and those that have failed?

    Result = Struct.new(:student, :mark)
    results = []
    results << Result.new("Toby", 35)
    results << Result.new("Phil", 45)
    results << Result.new("Susan", 80)
    results
    => [#<struct Result student="Toby", mark=35>, #<struct Result student="Phil", mark=45>, #<struct Result student="Susan", mark=80>]
    passed, failed = results.partition{|r| r.mark > 50 }
    => [[#<struct Result student="Susan", mark=80>], [#<struct Result student="Toby", mark=35>, #<struct Result student="Phil", mark=45>]]

## What do you use partition for?

Hopefully this has been helpful to you if you didn't know partition existed or
weren't 100% sure how to use it.

If you are a long term user of this particular method I would love to know what
novel things you have done with it.
