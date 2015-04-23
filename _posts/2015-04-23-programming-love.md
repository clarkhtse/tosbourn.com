---
layout: post
title: I love programming
categories:
- General
tags:
- Love
- Little Logs
---

This evening I wrote a quick script whilst I was waiting for my dinner to arrive. It was a lovely Indian from a place close to me in Hammersmith, since you asked.

The script does something that not a lot of people will want or care about, it performs an incredibly simple job that you could easily argue *I* shouldn’t care about, and it was written without too much care or consideration.

That all being said I still love it, and it reminded me why I love programming.

## Immediate Feedback

Like the “Hello World” examples we all loved writing when learning our first languages this was a script that at all stages gave me immediate feedback – I could see things taking shape right before my eyes.

## Adding Value

Even though I prefaced this article by saying not a lot of people will want or care about this script, I feel like I have taken something and made a small part of it better. Chances are 1 other people in the world will agree and I have been able to contribute to adding value.

## Building Blocks

The script relies on the fact you can easily send email from the command line in most *Nix systems. This meant I didn’t have to do any heavy lifting with networking.

It also is ran from an interface introduced by Bash. I haven’t hard to package up this program or compile it for it to be executable or runnable.

## I Learned Something

Actually I learned several things.

* How the `mail` command works from the command line (on OS X at least)
* That `<<-HEREDOC` syntax in Bash can only have text within it spaced with tabs, indenting with spaces doesn’t work
* When writing README.md files in Github you can reference images in your repository without needing a full URL or for them to be uploaded to a third party service.

I freaking love learning stuff, even if it is seemingly trivial or stuff that it feels like I may never need again.

## The script

The script lets me update [Little Logs](http://littlelogs.co) from the command line.

[You can see it on Github](https://github.com/tosbourn/littlelogs-cli).