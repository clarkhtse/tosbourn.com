---
layout: post
title: Good Habits for Student Developers – Documentation
categories:
- Students
tags:
- 
---
This is my third post in a series of three about what I consider to be good habits for student developers to embrace and start formalising early.

In this article I will be covering documentation. In the previous two I have tackled [time keeping](/good-habits-for-student-developers-time-keeping/) and [backups](/good-habits-for-student-developers-backups/).

Documentation is crucial to web development and unfortunately it isn’t a skill that is readily taught on many courses and it isn’t something that many employers are going to thank you for spending time on. 

Think of all the code libraries you use were you have had to look up examples of using the code, or reading the documented source code to see what things you can pass into a certain method. It is important. 

Luckily, I think that with a bit of practice you can get pretty good at writing decent documentation pretty quickly, at least enough to get by and to be a net positive on your team. 

## Documenting Problems

The first way you can really help your team is by properly documenting issues you have spotted. Well documented issues will tell the story of the issue and sometimes inadvertently hint at some possible solutions. 

When writing down a problem you need to try and think about what someone with minimal context would need in order to start forming a solution. 

If you are writing an issue that sometimes the title of a page gets cut short, you could just write “fix title getting cut short” and leave no description. 

If you are lucky you will remember the page you were talking about the next day. 

A better way to document this particular problem is to;

* Give an example page it is happening on. 
* Copy the offending title into the bug description. 
* Say the browser / device you were using. 
* Explain why you think this is a problem. 

This last point is crucial. Maybe the title getting cut short is by design, maybe your users detest long titles! In the issue you need to say why you think the system would be improved by fixing it. 

## Documenting Code

Code should be self documenting, what this means is your method names should be self explanatory. Your code should also be as forgiving as possible. 

If you have a method which reverses an array you should call it something like ‘reverse’ or ‘array_reverse’ (it depends on how your language of choice normally does things, were possible follow language conventions). 

If someone passed in a single element instead of an array you could throw an error, but perhaps their input normally is an array and just this time it is the one element. Instead of getting people to read documentation you could make sure your method coerces any input into an array before you get to work. So “1” would be treated as [“1”]. 

Having said that sometimes it is hard to write well thought out code in the timeframe you have been given, this is unfortunately just a reality of getting paid to write code. In these cases you should leave some code comments explaining the intent of the next block of code. 

Something I don’t use a lot but are an option are docblock comments you can write in code which stick to a predefined syntax for documenting methods. One of the great features about them is you can automatically generate documentation for your code based on these comments.

## Documenting Usage

Writing good code is something that you will continually improve at, something that won’t improve over time unless you practice it is documenting usage of your code.

If you are writing an API you should document what end points can be called, how and with what data. You should also show people what they would expect to get back from such a call.

If you are writing a piece of code that can be ran independently, like a rake task, you should document somewhere the correct usage.

Normally a README.md file is as good a place as any for things like this, at least in smaller projects.

The trick is to document as you go, don’t leave it as a task for the end because you will either not do it or will rush it, or you miss out on the chance to reflect – if code usage is complicated to explain then it is probably complicated to look at under the hood and you should consider improving it.

## Tests as Documentation

Someone should be able to read/execute your test suite and understand how the things being tested are meant to react.

When writing tests you should be descriptive about the thing under test. There is some really good advice over at [BetterSpecs](http://betterspecs.org/) on the subject of testing in general, I highly advise you read that site.

## Documenting your Progress

Documenting is all about helping other people understand what code is doing. Part of that is letting your colleagues and fellow contributors know how things are shaping up.

One of the easiest ways to do this is to write good commit messages when submitting your code into version control. Try not to write “Bug Fix” and instead start with a useful title and then explain the change in as much detail as possible – as with documenting issues you should stress why this code change makes the code or application better.

Pushing well documented changes regularly will keep whoever on the team wants to be kept abreast of changes well informed and removes the stress of having to remember every change you worked on last week when it comes up in a meeting!

## Wrapping Up

If you document as you go and make use of the tools provided by the version control systems, frameworks, and IDEs this doesn’t need to be a daunting thing and you will soon reap the benefits.

Hopefully this has been useful. If you have any questions about documenting please comment below – there are no stupid questions.
