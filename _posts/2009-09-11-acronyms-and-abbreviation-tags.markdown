---
layout: post
status: publish
published: true
title: Acronym and Abbreviation Tags
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 138
wordpress_url: http://www.tosbourn.com/?p=138
date: '2009-09-11 07:53:49 +0100'
date_gmt: '2009-09-11 06:53:49 +0100'
categories:
- Other
tags:
- Design
- abbr
- acronym
- html
comments: []
---
<p>I think these are two of the most under used tags in HTML, which is a shame because really quickly you can provide some excellent functionality and really help your users out with very little effort on your part.</p>
<p>So, what are they?</p>
<p>The Acronym tag or &lt;acronym&gt; to it's friends is a tag that should encapsulate all acronyms used on your website.  If you don't know what an acronym is I would have to <acronym title="Laugh out Loud">lol</acronym> at you and pass you across to <a href="http://www.google.co.uk/search?hl=en&amp;q=define%3Aacronym&amp;btnG=Search">this website</a>.</p>
<p>The Abbreviation tag, which has been nicely shortened (I see what they did there!) to &lt;abbr&gt; is a tag which should be used around any text that is an abbreviated form of a longer word.  I can't think of anything even slightly funny, so if you don't know what an abbreviation is then <a href="http://www.google.co.uk/search?hl=en&amp;q=define%3Aabbreviation&amp;btnG=Search">go here</a>.</p>
<p><a href="http://www.w3.org/TR/html401/struct/text.html">w3.org</a> have the following to say on the subject of acronyms and abbreviations.</p>
<blockquote><p>The ABBR and ACRONYM elements allow authors to clearly indicate occurrences of abbreviations and acronyms. Western languages make extensive use of acronyms such as "GmbH", "NATO", and "F.B.I.", as well as abbreviations like "M.", "Inc.", "et al.", "etc.". Both Chinese and Japanese use analogous abbreviation mechanisms, wherein a long name is referred to subsequently with a subset of the Han characters from the original occurrence. Marking up these constructs provides useful information to user agents and tools such as spell checkers, speech synthesizers, translation systems and search-engine indexers.</p>
<p>The content of the ABBR and ACRONYM elements specifies the abbreviated expression itself, as it would normally appear in running text. The title attribute of these elements may be used to provide the full or expanded form of the expression.</p></blockquote>
<p>So now you know what they are and when they should be used, I guess I should write about why you should use them.</p>
<p>First off you would be scoring a really quick win as far as <a href="http://www.w3.org/TR/WCAG10-HTML-TECHS/#text-abbr">WCAG</a> is concerned, checkpoint 4.2 to be exact.</p>
<blockquote><p>Specify the expansion of each abbreviation or acronym in a document where it first occurs. [Priority 3]</p></blockquote>
<p>Secondly, it is semantic - You could argue that this is getting really pedantic in your markup, but it makes sense because the words we encapsulate with these tags are different from normal text.</p>
<p>My third and final point on why I think you should be using it is because it is useful to the end user, accessibility aside it is just nice to get a really quick definition of what an acronym on your site is.</p>
<p>In the past I have found a lot of websites that would use a fairly specific acronym to their area of interest and they would wrap an &lt;a&gt; around it and link off to wikipedia, when I think &lt;acronym&gt; along with the context the actual acronym is mentioned in would be more than enough for most users, and those that still don't know - there is always google!</p>
<p>I guess it is time I actually mentioned how you use them, it is really straight forward.</p>
<p>&lt;acronym title="This is my Acronym"&gt;TIMA&lt;/acronym&gt;</p>
<p>&lt;abbr title="Personal Identification Number"&gt;Pin&lt;/abbr&gt;</p>
<p>That is it, easy eh?</p>
<p>I would like to know people's opinions on this, but my thoughts are that you shouldn't do too much extra styling to these elements other than what you would normally do to the text on your site.  Let the browser handle it the way it wants to, which is normally with a dashed line underneath which I think is fairly universal and looks pretty nice.</p>
