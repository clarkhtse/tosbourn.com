---
layout: post
status: publish
published: true
title: View Markdown Files in your Terminal
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2498
wordpress_url: http://tosbourn.com/?p=2498
date: '2015-01-20 13:43:51 +0000'
date_gmt: '2015-01-20 12:43:51 +0000'
categories:
- Development Help
tags:
- Markdown
- Lynx
comments:
- id: 684
  author: Nicklas
  author_email: n@takete.com
  author_url: ''
  date: '2015-01-20 13:53:00 +0000'
  date_gmt: '2015-01-20 12:53:00 +0000'
  content: This changes everything!
---
<p>I spend all day in my terminal and for better or worse I deal with a lot of Markdown files throughout the day.</p>
<p>One thing I often find myself needing to do is preview or read a markdown file, a lot of the time this could be a README.md for a project I am coming back to or maybe a blog post that is sitting in draft somewhere.</p>
<p>I decided to write a very quick function that would facilitate previewing Markdown files in the terminal. I wanted to share this because I am sure this annoys more than just me!</p>
<p>There are two programs I am using to help me do this.</p>
<p>The first is <a href="http://johnmacfarlane.net/pandoc/">Pandoc</a>, which is great at taking things like Markdown and changing it into something else (say, HTML).</p>
<p>The second is <a href="http://en.wikipedia.org/wiki/Lynx_%28web_browser%29">Lynx</a>, which is a text based web browser that you can run in your terminal.</p>
<h2>Installing Pandoc and Lynx</h2>
<p>On OS X I would recommend installing these using homebrew.</p>
<p><code>brew install pandoc</code></p>
<p><code>brew install lynx</code></p>
<p>If you are running Linux, your package manager of choice should have them.</p>
<h2>Setting up the script</h2>
<p>Once you have these installed the helper function we need to join them together is very simple.</p>
<p>Open up <code>~/.profile</code> or whatever text file you like using for your terminal preferences and paste the following;</p>
<pre><code>rmd () {
  pandoc $1 | lynx -stdin
}
</code></pre>
<p>What this does is defines a function called rmd (Read Markdown) and in the body of the function it tells Pandoc to read in whatever file you have specified and pass this to lynx which will be listening for standard input.</p>
<p>Once you have this in and have saved your file you will need to run <code>source ~/.profile</code> (or whatever file you edited).</p>
<h2>Usage</h2>
<p>To use this just call <code>rmd path/to/markdowndown/file.md</code> and it will open up as a webpage in Lynx.</p>
<p>To quit out of Lynx just press q and you will be back to your terminal.</p>
<p>Because Lynx is a fully fledged browser you can follow links in the markdown file and interact just like you would if you were viewing it in your normal browser.</p>
