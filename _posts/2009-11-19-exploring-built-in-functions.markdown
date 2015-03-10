---
layout: post
status: publish
published: true
title: Exploring Built In Functions
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 186
wordpress_url: http://www.tosbourn.com/?p=186
date: '2009-11-19 01:12:02 +0000'
date_gmt: '2009-11-19 00:12:02 +0000'
categories:
- Other
tags:
- Development
- Functions
comments: []
---
<p><img class="alignright size-medium wp-image-189" title="Screenshot" src="http://www.tosbourn.com/wp-content/uploads/2009/11/Screenshot-300x261.png" alt="Screenshot" width="300" height="261" />An issue I have been pondering lately is how much time to dedicate to trawling through programming language manuals and doc files looking for built in functions to perform a particular task.</p>
<p>Obviously there are some functions that you can pretty much take for granted will be provided for by the language, an example would be returning the size of the array.  We know that each language might have slightly different terminology for performing this basic task but we also know it should be there and is most likely going to be easy to find - a very quick google will tell you what you need to know and you can carry on with your life.</p>
<p>But what about some of the more fiddly functions?  An example would be the large array*<sup>1</sup> of functions you can call in PHP to do some fairly cool stuff to arrays and I know that the majority of these functions are not going to be available in say JavaScript.  Normally I would have a quick google and if nothing immediately jumps out at me and I know I have a rough idea of how to recreate this bit of code then I will just go ahead and write it myself.  I think there are a few pros and cons to what I do.</p>
<p>Pros;</p>
<ul>
<li>I get to think about the best way to make these functions.</li>
<li>I get to create the function exactly how I want.</li>
<li>I get to create!</li>
<li>I am not wasting time searching for something that may not exist.</li>
</ul>
<p>Cons;</p>
<ul>
<li>It is generally going to be slower to write it from scratch than it would be to spend some more time digging about to find the appropriate function.</li>
<li>I am not fully getting my teeth into the language or taking benefit from its internal libraries.</li>
<li>If there is an in built method already in place, I am sure it is going to be far more optimised for the task than my method is*<sup>2</sup></li>
</ul>
<p>Lets now say that we have looked through the manual for the language and done some googling and we are pretty confident that a function doesn't exist natively, it seems to me that we then have a couple of choices; we can see if someone else has created similar methods/libraries/functions or we can create them ourselves.  Obviously there are pros and cons to finding someone else's.</p>
<p>Pros;</p>
<ul>
<li>Can be quicker.</li>
<li>Already documented.</li>
<li>Sometimes there is community support</li>
</ul>
<p>Cons;</p>
<ul>
<li>It will never do 100% what you want it to do.</li>
<li>You will never learn how to solve the problem for yourself (but if there is a solution, then is it worth you solving it again?)</li>
</ul>
<p>The pros and cons for creating it yourself is pretty much the reverse of the above!</p>
<p>I guess what I am asking, in a rather round about way, is how much time do you spending searching for a pre-built solution against writing your own?</p>
<blockquote><p>*<sup>1</sup> - Do you see what I did there? An array of functions? Har har har!!<br />
*<sup>2</sup> - Actually, I am not convinced this is true, most in built functions have to be fairly generic, I can streamline my functions to do what I want them to do, but for example I know that creating a function to return the size of an array is going to be less efficient at run time than using sizeof(), no matter what awesome stuff I do within that method.</p></blockquote>
