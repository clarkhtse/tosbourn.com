---
layout: post
status: publish
published: true
title: Checking if a password field is present in Selenium.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 605
wordpress_url: http://tosbourn.com/?p=605
date: '2011-10-13 07:16:15 +0100'
date_gmt: '2011-10-13 06:16:15 +0100'
categories:
- Development Help
tags:
- Selenium
comments:
- id: 107
  author: Jason
  author_email: jason.alexander.az@gmail.com
  author_url: ''
  date: '2012-02-02 03:34:00 +0000'
  date_gmt: '2012-02-02 02:34:00 +0000'
  content: "unsure how to exactly to do this.  Here is what I tried:\n\nisElementPresent(\"//input[@id='password'
    and @type='password']\"), \"Verified password is present and masked\");     \n       
            \nany feedback would be appreciated."
---
<p>Many people fall into the (understandable) trap of treating Password fields like Text fields when testing them in Selenium.</p>
<p>If you have made this mistake then you may be stuck wondering about how to test for masking in the field (<a href="http://stackoverflow.com/questions/5029748/how-to-check-whether-password-field-is-encrypted/5029784#5029784" target="_blank">like this chap was</a>) the answer, of course, is to assert that input of type password and id of whatever exists on the page.</p>
