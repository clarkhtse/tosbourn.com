---
layout: post
status: publish
published: true
title: Edit an option of a select menu using jQuery
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 410
wordpress_url: http://www.tosbourn.com/?p=410
date: '2011-03-21 20:07:08 +0000'
date_gmt: '2011-03-21 19:07:08 +0000'
categories:
- Development Help
tags:
- html
- jQuery
comments: []
---
<p>I have read many articles that cover how to use jQuery to add and remove options from a select box but I couldn't find one that covered how to edit an individual option.</p>
<p>I knew there had to be a way and the good people of Stack Overflow were able to answer <a href="http://stackoverflow.com/questions/5380704/setting-the-text-of-an-option-element-using-jquery/5380764#5380764" target="_blank">my question</a>.</p>
<p>Essentially what you need to do is use the option selector in order to grab the element you want, then it is fairly trivial.</p>
<pre>$('#selectID option[value="knownValue"]').text('New Option Text');</pre>
<p>So what we are saying here is for every element with the ID of 'selectID' look for an option with the value of 'knownValue'.</p>
<p>Change the text of that option to 'New Option Text'.</p>
<p>A use case for this (and indeed the reason why I was looking it up) is that if you have a collection of objects and you want to edit them dynamically by selecting them via dropdown then edit the fields you will most likely want to edit the 'name' field or some other field that represents the unique name which appears in the dropdown list.</p>
<p>If this is the case when you edit your name and hit save, assuming it is all done using ajax the value in the dropdown will no longer equate to the value stored in the database. This is a usability concern so you should use the method above to ensure that the option text of the dropdown gets edited accordingly.</p>
