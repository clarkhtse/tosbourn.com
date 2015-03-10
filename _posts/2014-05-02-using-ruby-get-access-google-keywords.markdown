---
layout: post
status: publish
published: true
title: Using Ruby to get access to Google Keywords
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1875
wordpress_url: http://tosbourn.com/?p=1875
date: '2014-05-02 21:48:12 +0100'
date_gmt: '2014-05-02 20:48:12 +0100'
categories:
- Other
tags:
- Ruby
- Google Adwords
- Keywords
comments: []
---
<p>This is a short post detailing at a high level how you would go about using Ruby to get access to Google keyword suggestions.</p>
<p>First of all Google's Keyword API is hooked into their Adwords API, this means a valid Adwords account will be required to gain access to the API.</p>
<p>Accounts are free, essentially any Google account can sign up, it doesn't appear that you need to have any active campaigns going or anything like that in order to use the Keywords.</p>
<p>There is a <a href="https://github.com/googleads/google-api-ads-ruby">Ruby implementation of Google Adwords API</a> and there is a <a href="https://github.com/googleads/google-api-ads-ruby/blob/master/adwords_api/examples/v201402/optimization/get_keyword_ideas.rb">specific code example that deals with Keywords</a>.</p>
<p>The API works as one might expect, you feed it a keyword and it returns multiple suggestions of other keywords and you should note that there doesn't appear to be any cost for using this service.</p>
<p>You should note and you probably noticed if you have looked at the code sample that is uses a SOAP interface to make calls, this won't be just as pretty as some of the slick JSON APIs you are maybe used to, but it will get the job done!</p>
<p>&nbsp;</p>
