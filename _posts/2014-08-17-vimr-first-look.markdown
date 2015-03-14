---
layout: post
status: publish
published: true
title: VimR - A first look
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2289
wordpress_url: http://tosbourn.com/?p=2289
date: '2014-08-17 00:07:19 +0100'
date_gmt: '2014-08-16 23:07:19 +0100'
categories:
- Other
tags:
- VimR
comments:
- id: 558
  author: Jilles
  author_email: info@jilles.me
  author_url: http://jilles.me
  date: '2014-08-17 21:36:00 +0100'
  date_gmt: '2014-08-17 20:36:00 +0100'
  content: |-
    A way to set a default opening directory – Right now we need to open it and immediately open a new project.
    You could add this to your ~/.vimrc:


    cd ~/Projects


    That's what I have, works great!
- id: 559
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-08-18 09:27:00 +0100'
  date_gmt: '2014-08-18 08:27:00 +0100'
  content: |-
    That is really useful, thanks!

    I have also been shown a way to open VimR from the command line: http://tosbourn.com/running-vimr-command-line/
- id: 636
  author: pnel
  author_email: pierre.nel@gmail.com
  author_url: ''
  date: '2014-11-15 11:30:00 +0000'
  date_gmt: '2014-11-15 10:30:00 +0000'
  content: |-
    I've been using:

    open -a 'vimr' .

    to fire up vimr in a project directory :-)
---
<p><img class="alignright size-medium wp-image-2290" src="http://tosbourn.com/wp-content/uploads/2014/08/vimr-icon-300x300.png" alt="vimr-icon" width="300" height="300" />Recently I noticed a post on <a href="https://news.ycombinator.com/item?id=8186407" target="_blank">Hacker News</a> about something called VimR, the full title was VimR - Refined Vim Experience for OS X.</p>
<p>As someone who a) uses Vim, b) runs OS X and c) enjoys refined experiences this had my attention.</p>
<p><strong>Note</strong> - The version I am using is v0.1.5, the creator has stated in several places that this is still very much a work in progress</p>
<h2>What is VimR</h2>
<p>So what is <a href="http://vimr.org/" target="_blank">VimR</a> (apart from a refined Vim Experience for OS X!)?</p>
<p>The quick answer is that it is a more visual Vim environment, not dissimilar to MacVim.</p>
<p>The slightly longer answer, if I follow what people have been saying correctly is that this an implementation of the MacVimFramework. <a href="https://github.com/qvacua/macvim" target="_blank">MacVimFramework</a> is a fork of MacVim which has been tweaked so that it can be used inside other projects.</p>
<p>To quote the creator of VimR, Tae Won Ha;</p>
<blockquote><p>So, to summarize: the rationale behind VimR is to build an editor which offers the full Vim experience, even if I don’t use all features of Vim, but has other convenience features—found in many other editors and in Vim scripts—in a graphical form, improving the whole editing experience.<br />
<cite><a href="http://ishouldcocoa.net/post/85242609106/why-vimr">Tae Won Ha</a></cite></p></blockquote>
<h2>How do you Install VimR</h2>
<p>If you have installed any Mac apps before from a website this won't be new to you but if you haven't the process is very simple;</p>
<ul>
<li>Visit the official website of <a href="http://vimr.org/" target="_blank">VimR</a></li>
<li>Click the Download link, this will download a compressed file</li>
<li>I have my machine set up to auto extract compressed files once downloaded, if you don't you will need to extract the file.</li>
<li>Drag or move the extracted file 'VimR.app' into your Applications folder</li>
</ul>
<h2>First Impressions of VimR</h2>
<p>The very first time I opened up VimR my immediate first impression was "Yes! They use Solarised" which is the colour scheme that I use in my normal vimmings! Of course then I realised that this isn't another copy of Vim, this *is* Vim, so it is reading my vimrc - which means no settings to change :-)</p>
<p>The sidebar file browser defaults to your home directory, which makes sense, I looked to see if I can configure this and at the moment you don't seem to be able to.</p>
<p><a href="http://tosbourn.com/wp-content/uploads/2014/08/Screenshot-2014-08-16-23.17.38.png"><img class="size-large wp-image-2291" src="http://tosbourn.com/wp-content/uploads/2014/08/Screenshot-2014-08-16-23.17.38-1024x640.png" alt="Opening Screen VimR" width="474" height="296" /></a> Opening Screen VimR</p>
<p>The first thing I wanted to do is open a project I have been working on to get a feel for how it acts on a project. To do this I pressed CMD+O.</p>
<p>Everything looks good. It noticed I was using Python and has applied syntax highlighting correctly, I can also see just the two files that are in this project (see the following image)</p>
<p><a href="http://tosbourn.com/wp-content/uploads/2014/08/Screenshot-2014-08-16-23.20.05.png"><img class="size-full wp-image-2293" src="http://tosbourn.com/wp-content/uploads/2014/08/Screenshot-2014-08-16-23.20.05.png" alt="Project view of VimR" width="641" height="375" /></a> Project view of VimR</p>
<p>This is maybe a silly project to test with, but by pressing CMD+Shift+O I was able to get into Quick Open which allows me to start typing filenames in a fuzzy way and when I tested it on a large rails project it works great.</p>
<h2>Things I hope come soon to VimR</h2>
<p>I don't know if Tae Won Ha will ever read this, but if he does, first of all hi and thank you! and secondly, here are some things I would love to see implemented at some stage;</p>
<ul>
<li>Being able to open the app from the command line - I tried a few different methods but couldn't get my current path passed in correctly. (<a href="https://github.com/qvacua/vimr/issues/99">I have reported this</a>)</li>
<li>Being able to make the app full screen - This is fairly common functionality across most OS X apps at this point. (<a href="https://github.com/qvacua/vimr/issues/45">Covered by this issue</a>)</li>
<li>A documented or easy way to add plugins - Right now prior knowledge of Vim is assumed.</li>
<li>A way to set a default opening directory - Right now we need to open it and immediately open a new project.</li>
</ul>
<h2>The VimR Codebase</h2>
<p>If you know Objective-C (I don't) then you may want to have a look around the <a href="https://github.com/qvacua/vimr">codebase</a>.</p>
<p>I have pulled it down and opened it in X Code, like I say I don't speak Objective-C but it seemed intuitive enough to work around, it is interesting to see how it hangs together.</p>
<h2>VimR Sounds Stupid, why not use MacVim or Vim?</h2>
<p>A commenter on the original Hacker News article I linked to said it better than I could;</p>
<blockquote><p>I love the negativity in many of the responses here. Obviously people like native apps. Macvim is a thing. Emacs has a gui version for os x. Sublime is a thing. This is a polished port of macvim that has a file drawer, which is a feature that many people want baked into macvim. Browsing complex file hierarchies and large projects isn't great inside a terminal, and is a giant hurdle for many new users of vim.</p>
<p>If this isn't for you then fine but don't rush here to proudly proclaim how you don't understand the point of this. I don't know why anyone submits their pet projects here.<br />
<cite><a href="https://news.ycombinator.com/item?id=8186703">Poolpool</a></cite></p></blockquote>
<h2>Playing with VimR</h2>
<p>Sure there are some things that are what I would consider to be missing, but I think I will continue playing with VimR with a view to it replacing terminal Vim as my main editor. </p>
<p>The fact that it is still Vim at its core means that should I need to jump back to Vim in the terminal there will be no muscle memory lost.</p>
<h2>Some VimR Resources</h2>
<p>Just in case you want to know more, here is a list of the resources I have used for this write up :-)</p>
<ul>
<li><a href="http://vimr.org/" target="_blank">Official VimR Website</a></li>
<li><a href="https://twitter.com/VimRefined" target="_blank">Official VimR Twitter Account</a></li>
<li><a href="https://github.com/qvacua/vimr" target="_blank">The VimR Git Repository</a></li>
<li><a href="http://usevim.com/2014/05/07/vimr/" target="_blank">UseVim article introducing VimR</a></li>
<li><a href="https://twitter.com/hataewon" target="_blank">Tae Won Ha's Twitter Account</a></li>
<li><a href="http://ishouldcocoa.net/post/85242609106/why-vimr">Tae Won Ha talking about why he made VimR</a></li>
</ul>
<p>&nbsp;</p>
<p>&nbsp;</p>
