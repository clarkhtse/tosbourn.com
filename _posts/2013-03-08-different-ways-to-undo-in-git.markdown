---
layout: post
status: publish
published: true
title: Different ways to undo in Git
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1338
wordpress_url: http://tosbourn.com/?p=1338
date: '2013-03-08 12:49:52 +0000'
date_gmt: '2013-03-08 11:49:52 +0000'
categories:
- Development Help
tags: []
comments:
- id: 657
  author: wow gold guide
  author_email: otpmqsjog@gmail.com
  author_url: http://www.sobond.org/news
  date: '2015-01-01 13:30:09 +0000'
  date_gmt: '2015-01-01 12:30:09 +0000'
  content: "Video game titles each week were initially destroy all the characters
    2 along with the WiiWare title muscles March. Hang in there to make Pacmobelia
    possibility for triumph in an expression in the bottom to on an Xbox 360 month.
    A fantastic Xbox 360 was distributed relating to the past month's players, A complete.
    I am only cute luxurious. Probably including massively duper luxurious.\r\n[url=http://www.sobond.org/news]wow
    gold guide[/url]"
---
<p>Git has a load of ways to undo stuff and each of them has pros and cons. In this post I just want to highlight some use cases that can crop up during development and the git command that I recommend you run in order to overcome them.</p>
<h2>When you edit a file and you want to undo it to the point of your last commit.</h2>
<p>If you have made multiple changes to a file and you decide that they are all a bit rubbish or unnecessary (this happens more than I would like to admit) then you can undo everything to the point of your last commit by typing;</p>
<p><code>git checkout -- file_1.txt</code></p>
<h2>When you edit a group of files and want to undo them all to the point of your last commit.</h2>
<p>The process for if you want to repeat the above for multiple files is largely the same, I wanted to bring it out into its own section because I wanted to issue a word of warning first. Running the following code will revert all changed files back to their last committed state, which is fine so long as you are aware of what all those files are. I would advise running <code>git status</code> to confirm that all the modified files you are about to change are what you would expect.</p>
<p>So long as you are happy the code you would need to run is;</p>
<p><code>git checkout -- .</code></p>
<p>You can also run a slightly safer command by chaining all the files together like this;</p>
<p><code>git checkout -- file_1.txt file_2.txt</code></p>
<p>Finally you can run the same command on only .txt files by typing;</p>
<p><code>git checkout -- *.txt</code></p>
<h2>When you want a file to revert to an earlier commit and you want the history to be kept.</h2>
<p>It might be that you have been working on something for a while and after a few commits you realise that things just aren't going to work out, depending on the branching model you use you might just want to kill the branch, but if you want to keep the branch you are in and just go back to an earlier commit you can run the following commands.</p>
<p>First we want to know the hash for the commit we want to get back to;</p>
<p><code>git log</code></p>
<p>This will show all the commits for the branch you are currently in, the string you are looking for will be a hash that looks something like <code>36d5e484cbb7df38d852b3875d09d8d9656c1aa4</code></p>
<p>Once you have this you can run the following command;</p>
<p><code>git checkout 36d5e484cbb7df38d852b3875d09d8d9656c1aa4 file_1.txt</code></p>
<p>You will need to commit the fact you have reverted back.</p>
<p>If you wanted to go back to the version right before <code>36d5e484cbb7df38d852b3875d09d8d9656c1aa4</code> was made then you can run the following;</p>
<p><code>git checkout 36d5e484cbb7df38d852b3875d09d8d9656c1aa4~1 file</code></p>
<h2>When you want your entire project to revert to an earlier commit and you want the history to be kept.</h2>
<p>Just like when I shared the code for reverting a group of files back to your last commit you can pass some parameters that will apply a checkout to the entire project.</p>
<p><code>git checkout 39446e62247e84f318ca863e8665fa5b18df4c13 .</code> will revert all files back to the commit at <code>39446e62247e84f318ca863e8665fa5b18df4c13</code>.</p>
<p>Again you will need to commit your changes.</p>
<h2>When you want a file to revert to an earlier commit but you do not want the history to be kept.</h2>
<p>I do not know how to do this, answers on a postcard to <a href="https://twitter.com/tosbourn">@tosbourn</a> please!</p>
<h2>When you want an entire project to revert to an earlier commit and you do not want the history to be kept.</h2>
<p>If you just don't care about your history and want to quickly move the entire project back to a point in time, there is a command for that. Honestly this isn't something I have had to do except in tutorials, but it seems to come up for others.</p>
<p>First we will want to find the hash for the commit we want to go back to, then we would run the following code;</p>
<p><code>git reset --hard 39446e62247e84f318ca863e8665fa5b18df4c13</code></p>
<p>After running the command if you run <code>git log</code> you will see that any commits made after the commit in your hash will no longer be there.</p>
<h2>You want to temporarily ignore changes made to your project.</h2>
<p>If you want to temporarily ignore changes you have made since your last commit you can do so with the following command;</p>
<p><code>git stash</code></p>
<p>This will take your changes out of the loop momentarily.</p>
<p>When you want to incorporate them back in again you can run;</p>
<p><code>git stash pop</code></p>
