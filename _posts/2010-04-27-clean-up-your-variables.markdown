---
layout: post
status: publish
published: true
title: Clean up your variables
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 229
wordpress_url: http://www.tosbourn.com/?p=229
date: '2010-04-27 11:50:31 +0100'
date_gmt: '2010-04-27 10:50:31 +0100'
categories:
- Development Help
tags:
- PHP
- Variables
comments: []
---
<p>Clean data means data that we are sure is the correct type and is safe to insert into functions, tables etc.</p>
<p>One of the main advantages of cleaning data (aside from security in the case of strings) is that if you can trust the data coming into your function then you can more easily debug potential problems in the function itself.</p>
<p>If data is not clean it is dirty, and dirty data should not be trusted.</p>
<p>I think the best approach for knowing what data is clean and what is dirty is to assume everything is dirty unless it has a $clean_ name.</p>
<p>I will be covering strings in a separate document because they are way more involved but for now lets look at....</p>
<p>Integers and Booleans</p>
<p>These are the easiest things to cleanse because it is simply a case of casting the dirty variable into a clean one, for example..</p>
<blockquote><p>$clean_age = (int)$age;</p></blockquote>
<p>This way you know that $clean_age is definitely an integer, but how do you know it is the right integer?</p>
<p>Well if String is passed in with a non-numeric character at the start then the result will be zero, however if I pass “5test5” in the result would be 5.</p>
<p>Clearly this isn’t great, so before we begin to cleanse data we need to make sure we have the correct data, if we don’t then we can assume either something malicious or stupid has happened.</p>
<p>We could use something like this;</p>
<blockquote><p>if(is_int($age))<br />
{<br />
$clean_age = (int)$age;<br />
}<br />
else<br />
{<br />
die(‘Killing the script may sound harsh, but it is the right thing to do.  It is the only way we can develop bullet proof code’);<br />
}</p></blockquote>
<p>The exact same issue occurs with Boolean data types, whilst it can convert empty Strings and other things to the correct value (TRUE or FALSE) there is a chance for unexpected results (passing most non-zero values will result in true) so use is_bool() to check for Booleans and (bool) to cast them.</p>
