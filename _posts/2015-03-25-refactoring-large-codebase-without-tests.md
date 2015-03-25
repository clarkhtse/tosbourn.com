---
layout: post
status: publish
published: true
title: What to do when refactoring a large codebase without tests
author:
  display_name: Toby
  email: toby.osbourn@googlemail.com
categories:
- Developer Help
tags:
- Codebase
---

Recently I was asked my opinion on how to tackle a large refactoring of a Rails application.

I think this is a common enough issue, you get landed a large body of work that is _sort of_ working but needs a big overhaul and of course there are little in the way of useful tests to help you!

I have been thinking on the issue and wanted to jot down my thoughts, I would welcome your opinion on it as well.

The majority of the code was inherited, there were some older tests written but they weren’t really testing what I feel they should be (a lot of them were exercising default Rails functionality) and there had been changes made that would make some of the tests fail anyway.

The way I looked at it there were 3 things we needed to consider.

* There is code that is no longer needed.
* There are tests that aren’t actually testing anything of value.
* There is code that doesn’t make sense. (this is the code we will actually want to refactor)

Here are my thoughts then on what to do with these three things.

Code that isn’t actually required (old functionality, unwanted features, half finished things that were never implemented) should be deleted without question. Any corresponding tests should go as well.

Tests that don’t test business objectives or provide any value to the codebase should be killed.

What we should then be left with is some code that we now need to refactor and some tests to act as a starting block.

As I said the system has been added to since the original tests were written so we can’t really trust these tests to be 100% accurate, my thinking here is that you should use them as the first port of call to ask questions about how the code should be working but shouldn’t assume they are 100% correct.

With the code that is left I think you need to take each current method and write new tests to exercise the intended use of that method.

Once those tests are passing you could start to look at how you can tidy up the code even further and maybe drive out some higher level tests.

## Completely Wrong?

I could be completely wrong in how I am approaching this. If you think I am, let me know in the comments!