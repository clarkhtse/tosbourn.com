---
layout: post
status: publish
published: true
title: Using Mozilla's Mortar and App stub for bootstrapping Firefox OS apps
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1275
wordpress_url: http://tosbourn.com/?p=1275
date: '2013-01-28 23:00:00 +0000'
date_gmt: '2013-01-28 22:00:00 +0000'
categories:
- Development Help
tags:
- Firefox OS
- Volo
- Node
- Mozilla
comments: []
---
<p>Sometimes the thing that can put someone off wanting to work on a project is the dreaded blank screen when you start. This is especially true when the thing you are building is relatively new and there haven't been that many templates created to give you a helping hand.</p>
<p>If you are wanting to get stuck into your first <a href="http://tosbourn.com/category/firefox-os/">Firefox OS</a> application then an excellent place to start is <del>learning HTML, CSS and JavaScript fundamentals</del> with <a href="https://wiki.mozilla.org/Apps/Mortar">Mozilla's Mortar</a> package.</p>
<p>Think of Mortar as a really quick way of hitting the ground running whenever you first start building a Firefox OS application. It is essentially a boiler plate.</p>
<p>The first thing you will need to do is get Node installed, this is out of the scope of this article but if you haven't already installed it you should, the installation on most setups is very easy and it gives you some awesome power, like for example setting up Firefox OS applications quickly!</p>
<p>Once Node is installed you should install <a href="http://volojs.org/">volo</a>, volo is what will be doing all of the heavy lifting for us. You can install this by running <code>npm install -g volo</code></p>
<p>Now you have the workhorse installed we need to target the boiler plate that volo can read and generate page(s) from. There are a couple of ways to do this but the method I like it to just reference it in one command <code>volo create my_funky_cool_app mozilla/mortar-app-stub</code>.</p>
<p>Once this runs (it will need to download the files associated with mozilla/mortar-app-stub) you will get some boilerplate code generated inside of</p>
<pre>my_funky_cool_app</pre>
<p>, if you go into it and open <code>www/index.html</code> you will see a big blue install button, that is the boilerplate code at work.</p>
<p>Performing an ls on the <code>www</code> directory will show you all your starter files and folders;</p>
<pre>    css		
    favicon.ico	
    img		
    index.html	
    js		
    manifest.webapp</pre>
<p>From top to bottom these files are;</p>
<ul>
<li>css - Where your CSS lives.</li>
<li>favicon.ico - The icon file for your index.html page.</li>
<li>img - Where your images live including your icon files.</li>
<li>index.html - The main page of your app.</li>
<li>js - Where your JavaScript lives.</li>
<li>manifest.webapp - The meta information about your app.</li>
</ul>
<p>Hopefully this should help get you up and running and avoid the coders block that can come with a blank file in front of you!</p>
