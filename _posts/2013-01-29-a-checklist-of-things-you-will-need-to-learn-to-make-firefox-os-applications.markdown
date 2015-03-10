---
layout: post
status: publish
published: true
title: A checklist of things you will need to learn to make Firefox OS applications
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1282
wordpress_url: http://tosbourn.com/?p=1282
date: '2013-01-29 01:01:18 +0000'
date_gmt: '2013-01-29 00:01:18 +0000'
categories:
- Development Help
tags:
- Firefox OS
comments:
- id: 175
  author: euamotricotar
  author_email: euamotricotar@gmail.com
  author_url: ''
  date: '2013-07-09 22:32:00 +0100'
  date_gmt: '2013-07-09 21:32:00 +0100'
  content: Thank you for writting this!
- id: 176
  author: euamotricotar
  author_email: euamotricotar@gmail.com
  author_url: ''
  date: '2013-07-09 22:32:00 +0100'
  date_gmt: '2013-07-09 21:32:00 +0100'
  content: Thank you for writting this!
---
<p>If you want to get into developing for Firefox OS there are several things you will need to consider, I would suggest running down this list and making sure you are happy enough with everything before you take on your first project.</p>
<p>Don't be daunted by this list, many of these things you will already know enough of.</p>
<ul>
<li><strong>Learn HTML5</strong> - Firefox OS makes use of the latest HTML5 features, so make sure you are up to snuff on the HTML5 inputs, and other elements that have been introduced. I would suggest having a read through the <a href="https://developer.mozilla.org/en-US/docs/HTML">MDN</a> to bring yourself up to speed.</li>
<li><strong>Learn CSS3</strong> - Like HTML5 Firefox OS makes use of the latest CSS3 features so again you should make sure you are up to snuff with the newer properties and syntax. Again the <a href="https://developer.mozilla.org/en-US/docs/CSS">MDN</a> can help, and I would also suggest getting your head around Media Queries.</li>
<li><strong>Learn JavaScript</strong> - For anything other than the most basic of apps you are going to have to get your hands dirty with JavaScript. A lot of people jump straight into learning libraries like jQuery, but I would advise you learn the language first before worrying about libraries. One book I would recommend everyone read is <a href="http://www.amazon.co.uk/gp/product/0596517742/ref=as_li_ss_tl?ie=UTF8&amp;camp=1634&amp;creative=19450&amp;creativeASIN=0596517742&amp;linkCode=as2&amp;tag=tosbourn-21">Douglas Crockford's JavaScript: The Good Parts</a>.</li>
<li><strong>Learn Mobile Specific JavaScript</strong> - Once you know 'standard' JavaScript I would advise learning some APIs that are specific to mobile development, one such API is the <a href="https://developer.mozilla.org/en-US/docs/DOM/window.navigator.battery">Battery API</a>, I have <a href="https://github.com/tosbourn/battery-heads-up">shared some code</a> that uses this in the past.</li>
<li><strong>Learn a good text editor</strong> - If you are new to development you will need to work your way around a good text editor, I would recommend <a href="http://www.sublimetext.com/2">Sublime Text 2</a>, it is cross platform, lightweight and has pretty much everything a web developer needs.</li>
<li><strong>Learn how to debug websites and apps</strong> - A good proportion of your time will be spent debugging and viewing the source of your website or app, so it would be beneficial to learn how to use your browser's debugging tools.</li>
<li><strong>Learn some good basic app design</strong> - <a href="https://developer.mozilla.org/en-US/docs/Apps/Tutorials/General/App_design">This guide</a> should get you started in the right place, they follow basic web development best practice. There is a good Firefox OS design guide at <a href="http://buildingfirefoxos.com/">buildingfirefoxos.com</a></li>
<li><strong>Learn about the Manifest</strong> - This is one of the more unique aspects of developing for Firefox OS, learn why you need one and how to write one. <a href="https://developer.mozilla.org/en-US/docs/Apps/Manifest">Here is a good guide</a> on the subject.</li>
<li><strong>Learn how to create icons for your app</strong> - Kind of like favicon's for your website your application needs icons to be used in shortcuts and in the marketplace. <a href="http://www.mozilla.org/en-US/styleguide/products/firefoxos/icons/">Mozilla have a styleguide</a> on the subject.</li>
<li><strong>Learn how to debug your app</strong> - Wait, didn't I just say that? I did, but you need to again, because once the application is installed you will need to be able to do more debugging. There is an excellent guide <a href="https://hacks.mozilla.org/2012/11/hacking-firefox-os/">here</a> on it.</li>
<li><strong>Learn how to test</strong> - For your app to stand up to any scrutiny you will need to write unit tests for it and for it to pass. Personally I like <a href="http://qunitjs.com/">QUnit</a>.</li>
<li><strong>Learn how to backup and version control your code</strong> - I would suggest learning the ins and outs of <a href="http://github.com">GitHub</a>.</li>
<li><strong>Learn how to deploy your application</strong> - Nearing the end of your project you will want to be able to upload your project to the relevant places. <a href="https://developer.mozilla.org/en-US/docs/Apps/Submitting_an_app">Mozilla have a good guide on this</a>.</li>
</ul>
<p>Happy developing!</p>
