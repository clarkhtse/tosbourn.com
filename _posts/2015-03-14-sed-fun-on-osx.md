---
layout: post
status: publish
published: true
title: Sed fun on OSx
author:
  display_name: Toby
  email: toby.osbourn@googlemail.com
categories:
- Developer Help
tags:
- ‘365’
- Sed 
- OSx
---

I recently moved from WordPress to Jekyll for managing my blog. The move went smoothly, the biggest content issue was that any images I had with captions were not in the correct format.

This meant that some of my posts were littered with text like `[caption id=...]` and `[/caption]`. I wanted to remove these tags.

## Enter sed

Sed is a unix tool that allows you to do text operations on files without needing to manually open them.

At the very basic level (which is how I was using it) think of it as a way to do global find and replace.

## Killing [/caption]

I wanted to look through every single post I have on this blog and remove any instance of the phrase `[/caption]`.

The line I ended up using was;

     find _posts -type f -exec sed -i “” “s/\[\/caption\]//g” {} \;

What this is saying is look for files in the _posts directory (where all Jekyll posts are) and with them execute the following command;

    sed -i “” “s/\[\/caption\]//g”

The `-i` flag tells sed to edit the file in place, if I didn’t have this I would need to specify and output file.

In the OSx variant of sed you can’t use the `-i` flag without specifying a backup file you would like to use. I didn’t care about having a backup file because everything was version controlled anyway so I had to pass in a blank string.

`“s/\[\/caption\]//g”` is the regex that sed uses to do a global find and replace. A simpler version would be `”s/find_me/change_to_me/g”`. I needed to escape the ‘[‘, ‘]’, and ‘/‘ characters.

So far, so good. Now I wanted to kill that opening [caption] line.

## Killing the opening [caption]

This is slightly harder to accomplish than our last task, for a start the regex is a little more complicated.

First, let me show you what code I ended up using;

    find _posts -type f -exec sed -i “” -E “s/\[caption(.*)\]//g” {} \;

There are a few differences here, both in the sed section;

    sed -i “” -E “s/\[caption(.*)\]//g”

First, we are using the -E flag, by default sed uses an older version of regex, setting the -E forces the new syntax to be used and we that to allow us to do the lookup we want.

The lookup itself is a bit more complicated, here we are saying it will start with `[caption` then have *something* then end with `]`.

## Improvements

In my use case the captions didn’t actually contain anything useful, if they did though instead of removing them I would want to convert them to a correctly formatted image caption.

The final regex I used worked but was a bit greedy – If there existed a second or third ‘]’ on the same line, everything would have been deleted from it.

## Update

[PunKeel](http://ungeek.fr) reminded me on twitter that if I used `(.*?)` it would do a minimal match instead of a more greedy one. Thanks!

<blockquote class="twitter-tweet" lang="en"><p>You&#39;re crazy <a href="https://twitter.com/tosbourn">@tosbourn</a> ! (“s/\[caption(.*)\]//g”, SedFun) Use (.*?) instead of (.*) (minimal match) D:</p>&mdash; ❄ PunKeel (@PunKeel) <a href="https://twitter.com/PunKeel/status/576854115059425280">March 14, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

