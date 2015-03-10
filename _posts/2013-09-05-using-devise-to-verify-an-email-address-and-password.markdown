---
layout: post
status: publish
published: true
title: Using Devise to verify an email address and password
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1652
wordpress_url: http://tosbourn.com/?p=1652
date: '2013-09-05 11:34:12 +0100'
date_gmt: '2013-09-05 10:34:12 +0100'
categories:
- Other
tags:
- Ruby
- Devise
- Validation
comments: []
---
<p>Devise is a very powerful tool for handling authentication in Ruby applications, so powerful in fact that sometimes when I need to do simple tasks I found I get a little drowned in the weight of people talking about use cases far more complex than the one I want to fulfill.</p>
<p>One such example is verifying an email address and password. I don't need to log the user in or associate them with any role or anything, I just want to know if the submitted email/password combination is a valid one.</p>
<p>My mistake was I was searching for help by searching for things like "Check Sign In Details" or "Verify Log In Details", which were returning results relating to a method called sign_in, which is very useful but not what I needed here.</p>
<p>Here is the code you need to verify if an email address and password combo is valid, this obviously assumes that you have devise already set up and working correctly on your user model.</p>
<pre><code>user = User.find_by_email(params[:email])
if user.valid_password?(params[:password])
  # Valid!
else
  # Not Valid!
end</code></pre>
<p>Pretty straightforward!</p>
