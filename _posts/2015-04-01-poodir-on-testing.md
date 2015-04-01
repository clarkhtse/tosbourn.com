---
layout: post
status: publish
published: true
title: POODIR On Testing
categories:
- Developer Help
tags:
- Sandi Metz
- POODIR
---

Recently I have been re-reading sections of Sandi Metz' book [Practical
Object-Orientated Design In
Ruby](http://www.amazon.co.uk/gp/product/0321721330/ref=as_li_tl?ie=UTF8&camp=1634&creative=19450&creativeASIN=0321721330&linkCode=as2&tag=tosbourn-21&linkId=TBK7YZXQXLXQXCFE).
If you are learning Ruby or Object-Orientated programming in general I cannot
recommend this book highly enough.

I am not reviewing the book in this post, but I wanted to quote some of the
great insights on testing that are mentioned within it.

The phrase that really grabbed me in the section on testing is "Intentional
Testing" – I love the thought of testing with intent, not just testing
everything but testing the things you know matter in your code.

I could just quote the entire chapter but that feels like copyright
infringement and like I say you really should [buy the
book](http://www.amazon.co.uk/gp/product/0321721330/ref=as_li_tl?ie=UTF8&camp=1634&creative=19450&creativeASIN=0321721330&linkCode=as2&tag=tosbourn-21&linkId=TBK7YZXQXLXQXCFE).

## Common Issues for New Folk

Sandi talks about the common issue new developers to testing have were the costs
of writing tests far outweigh the percieved benefits.

> These are programmers who believed themselves highly productive in their
> former test-not lives but who have creashed into the test-first wall and
> stumbled to a halt. Their attempts at test-first programming result in less
> output, and their desire to regain productivity drives them to revert to old
> habits and forgo writing tests.

This speaks so much to me as it is a trap I have fallen into several times in my
career and something I **really** need to kick them into touch and test-first
all the time.

## The Benefits of Testing

Normally we hear about the benefits of testing being around writing better code
with fewer bugs. Sandi dives into some other benefits.

- Finding Bugs and fixing them faster.
- Supplying Documentation you can trust.
- Deferring Design Decisions until you know more about what you are building.
- Supporting Abstractions
- Exposing Design Flaws

Out of this list I especially like "Supplying documentation you can trust". The amount of times I have had to debug something in a
project and the documention was saying one thing but the results I was seeing
would suggest something else. Only once you dig into the tests do you see that
the docs need updating and the tests tell the real story of the application.

> The story they [the tests] tell remains true long after paper documents become obsolete
> and human memory fails.

## And so much more

The book goes into great detail on when you should test and what you should be
exercising in your tests. I am going to end my article here as I don't want to
take up too much time when you could be [reading it
yourself](http://www.amazon.co.uk/gp/product/0321721330/ref=as_li_tl?ie=UTF8&camp=1634&creative=19450&creativeASIN=0321721330&linkCode=as2&tag=tosbourn-21&linkId=TBK7YZXQXLXQXCFE)!

Let me know if you have read the book and if you have any thoughts on the
section on testing.
