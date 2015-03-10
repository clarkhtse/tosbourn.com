---
layout: post
status: publish
published: true
title: The EU Cookie Law website
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1021
wordpress_url: http://tosbourn.com/?p=1021
date: '2012-05-01 21:05:44 +0100'
date_gmt: '2012-05-01 20:05:44 +0100'
categories:
- Other
tags:
- CSS
- HTML5
- The EU Cookie Law
- LESS
- Google Analytics
comments: []
---
<p>So over the weekend I launched <a href="http://www.theeucookielaw.com">The EU Cookie Law</a>.com, there are several firsts for me and interesting features that I wanted to discuss.</p>
<p>So the reason I decided to create this site was because I wanted to learn more about the law and how it applies to the projects I work on.</p>
<p>Initially I was going to write an in-depth blog post about it but then decided to use it as an excuse to play with some funky new toys I have been meaning to play with for a while.</p>
<h2>Learning about the law</h2>
<p>Even the process of learning about the law was pretty interesting - on a quick pass you find a handful of websites aimed at the law and a few articles on it, but nothing major - but if you start to refine your search you find that there are hundreds of people chatting about it and there are a lot of conflicting views - it really depended on how you worded your search .</p>
<p>There is a question here around how neutral you can make yourself whenever you search on the web, the tone of question could very well dictate the type of answer, but that is for another blog post.</p>
<p>This project was the first time in a long time that I set myself a homework - normally I skim read dozens of articles, follow a handful of tutorials and generally coast through new things (I strongly believe this to be the most efficient way to be an excellent generalist).</p>
<p>This time I gave myself the task of learning about something in depth, writing notes on it and then summarising those notes in a way I felt would be useful to others.</p>
<p>I really enjoyed the process and I certainly think I am going to set myself more tasks like this - instead of maybe just following a tutorial, really getting my teeth into each section and writing about it in a longer form format.</p>
<p>The final takeaway point for learning about the law was the law itself,<span style="color: #ff0000;"> <strong>it seriously sucks</strong></span>, if you want to know about the EU Cookie Law, naturally you should visit the site but essentially it is just a bollocks law set by people who clearly have no real grasp of the technical issues involved in policing or enforcing something like this - it will crush small/medium businesses and put European trade on the back foot. Complete rubbish.</p>
<h2>Technology</h2>
<p>So the reason I decided to make a site instead of writing a blog post was I wanted a reason to try out Twitter's Bootstrap - just to see if it was any good. Honestly, I found it confusing as hell - I can see the use as a bit of a quick template to get you going but the experience wasn't anywhere close to what I assumed it would be like. I wouldn't recommend it.</p>
<p>Whilst I was looking through the source of the Bootstrap I was reminded though of LESS, which extends CSS to allow it to do a whole manner of awesome things - LESS is just the bee's knees, you can add variables to your code and apply mathematical and graphic methods to them, for example you can darken a colour by a particular percentage, this is so freakin awesome and time saving you wouldn't believe.</p>
<p>I was worried it would be a bit of an arse to set up because I was developing on a machine that I haven't really had the time to set up yet - to be able to compile the LESS files down to CSS I needed to install a node package, to install a node package I needed to install node, to install node I needed to install homebrew and to install homebrew I needed to install Xcode. None of these steps was particularly hard to do, it was just annoying to have to do them!</p>
<p>Once all the dependancies were installed I was flying, there was even a build package already built for Sublime Text 2 (my current text editor of choice) So I can just type cmd+b to save my less file as a CSS file.</p>
<p>If you have been to the site you will see that it is <em>very</em> basic - it is really just one long article - I had decided to use HTML5 because frankly only the elderly are still writing in HTML &lt; 5, because there was nothing too fancy going on I didn't bother including modernizr.js and my tests showed that IE7 handled everything just fine, which is more proof (if proof be needed) that HTML5  should be the standard doctype for your markup.</p>
<p>I also used this project as an excuse to dick around with responsive design - before you get too excited the site doesn't do a massive pile, in fact it was designed to be flexible regardless of media queries, but I was able to write enough to get my head more around the concepts better than it had been before.</p>
<p>If you are looking and can't see it, it is because it is <em>that</em> subtle, basically the gutters of the page decrease away to almost nothing when viewing it on a very narrow screen.</p>
<h2>Analytics</h2>
<p>One of the contentious issues around the EU Cookie Law is that analytics such as Google Analytics is not seen as core site functionality, and as such people need to be given the option to be able to opt in or out of getting the GA tracking cookie.</p>
<p>Obviously I didn't want to have a site about the EU Cookie Law that breaks the law, so I decided not to install Google Analytics, or any other 3rd party analytics tools.</p>
<p>I have to say I forgot how much you get can out of the information stored by the likes of Webalizer that comes installed cPanel (which comes with my hosting) - on a project like this were my only real interest in analytics is to look at some visitor counts every so often Webalizer more than meets my needs. I am sure plenty would disagree with me but I am starting to wonder if I need to stop blindly putting GA code into my sites and instead work with what my server can log and give me.</p>
<p>Because I don't have that tracking code installed, or any social networking plugins it means I could get away without any JavaScript on the site at all.</p>
<p>It has been years since I have been able to write a project that was 100% HTML/CSS and I have to say it was liberating - no debugging to do, no overheads to be concerned about, brilliant.</p>
<h2>The Power of Hacker News / Reddit</h2>
<p>The only promotion I did upon launching the site was to submit it to both Hacker News and Reddit, I had over 1000 hits on the first day and the traffic is still going strong. I couldn't have asked for better!</p>
<p>Sorry for the long rambly post!</p>
