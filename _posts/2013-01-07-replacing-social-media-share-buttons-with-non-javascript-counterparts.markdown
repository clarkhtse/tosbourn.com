---
layout: post
status: publish
published: true
title: Replacing Social Media Share Buttons with non-JavaScript counterparts
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1221
wordpress_url: http://tosbourn.com/?p=1221
date: '2013-01-07 23:55:05 +0000'
date_gmt: '2013-01-07 22:55:05 +0000'
categories:
- Other
tags:
- html
- JavaScript
- Mobile
- Social Media
comments:
- id: 169
  author: appcrawlr
  author_email: weathermaps@gmail.com
  author_url: ''
  date: '2013-06-30 04:48:00 +0100'
  date_gmt: '2013-06-30 03:48:00 +0100'
  content: |-
    This is a easy way to get the share window to popup in a nice window.

    &lt;a href="#"

       onclick="

           window.open(

                   'https://www.facebook.com/sharer/sharer.php?u='+encodeURIComponent(location.href),

                   'facebook-share-dialog',

                   'width=626,height=436');

           return false;"&gt;&lt;img width="20" height="20" src="/images/icons/facebook32b.png" title="Share on Facebook." alt="Share this on Facebook."/&gt;



    almost as good as javascript version, but with zero latency
- id: 170
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-06-30 11:37:00 +0100'
  date_gmt: '2013-06-30 10:37:00 +0100'
  content: |-
    That makes sense, but I am not sure having the share window pop up like that is a big enough win to have a dependency on JavaScript.

    Because you are returning false after the window.open you could just have the href point to the share page as a fallback.
- id: 396
  author: Nantwich Weather
  author_email: darrenmcdean@gmail.com
  author_url: ''
  date: '2014-01-30 16:45:00 +0000'
  date_gmt: '2014-01-30 15:45:00 +0000'
  content: |-
    This works perfectly, thankyou!

    http://www.nantwich-weather.co.uk/
- id: 545
  author: Par Example
  author_email: askaraidarkhan@gmail.com
  author_url: ''
  date: '2014-08-07 05:48:00 +0100'
  date_gmt: '2014-08-07 04:48:00 +0100'
  content: "Hi Toby, \nHow do you specify urls in those links above? \n\n<a href=\"http://www.facebook.com/sharer/sharer.php?u=http%3A%2F%2Fexample.com\"
    rel=\"nofollow\">Facebook</a>"
- id: 546
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-08-07 10:07:00 +0100'
  date_gmt: '2014-08-07 09:07:00 +0100'
  content: In a real world situation you would replace the hardcoded URLs with a variable
    and have your system add the correct URL, just make sure to encode it.
- id: 654
  author: Advncesharp
  author_email: advancesharp.com@gmail.com
  author_url: http://advancesharp.com/
  date: '2014-12-31 19:27:00 +0000'
  date_gmt: '2014-12-31 18:27:00 +0000'
  content: "If you don't want to make your site slow to download the different JavaScript
    you need to use the HTML only, see this \n\nhttp://www.advancesharp.com/blog/1127/social-media-sharing-buttons-without-javascript"
---
<p>Social media share buttons are a bit of an expected feature on today's websites, love them or hate them they are probably going to hang around for a while.</p>
<p>Of course like anything on the internet there are arguments for and against them from a user experience point of view but one thing that there can be no arguments about is that they cause extra load on your webpage. All the major social media share icons as supplied by the services use JavaScript hosted on their websites.</p>
<p>What this means in practical terms is that if you have four social share buttons on your article you are adding in at least four additional network requests to your page load, obviously there are worse things you could be loading in, each of the major players is smart enough to serve up pretty good code, but that isn't the point — even the most efficient code in the world still requires a network request, a download, a parse, etc. etc.</p>
<p>Is this an issue? Probably not on your nice high-speed broadband, but is it an issue on your phone? You betcha. The entire reason I was looking at this in the first place was I received a bug report<sup>*</sup> for something I was working on that on some mobile browsers the page was reporting it was only 95% loaded when all assets appeared to be served and working. The asset that was not loaded was a Facebook share button and until it loaded the page was in a mobile loading state, which is not nice for the user.</p>
<p>At first I started looking at better ways to load in the buttons, and there are plenty of good ones (<a href="http://socialitejs.com/">http://socialitejs.com/</a> looked very good) but I started thinking about what I wanted to be doing which is passing the user over to their social networking site of choice to allow them to share my content.</p>
<p>Then in a moment of extreme clarity I remembered that HTML5 has an element that allows you to do just that, in fact it has been in HTML for a while, that's right, the <code>&lt;a&gt;</code> element, all I want to do is allow the user to jump onto their social network at their sharing page and all the major ones allow it and HTML has supported links for a very long time.</p>
<p>Here is some sample code showing the four social networks I decided to target (including the actual links used in my project, I am too lazy to change them):</p>
<pre><code>
Share us on 
&lt;a target="_blank" href="http://www.facebook.com/sharer/sharer.php?u=http%3A%2F%2Fdigitalcreativejobs.com"&gt;Facebook&lt;/a&gt; 
&lt;a target="_blank" href="https://twitter.com/intent/tweet?text=Find%20a%20digital%2C%20creative%20job%20in%20%23NI%20&amp;url=http%3A%2F%2Fdigitalcreativejobs.com&amp;via=tosbourn"&gt;Twitter&lt;/a&gt; 
&lt;a target="_blank" href="https://plus.google.com/share?url=http%3A%2F%2Fdigitalcreativejobs.com"&gt;Google+&lt;/a&gt; 
&lt;a target="_blank" href="http://www.linkedin.com/shareArticle?mini=true&amp;url=http%3A%2F%2Fdigitalcreativejobs.com&amp;title=Digital%20Creative%20Jobs%20in%20Northern%20Ireland&amp;summary=Find%20a%20job%20in%20the%20Northern%20Irish%20Digital%20Creative%20Industry&amp;source=Digital%20Creative%20Jobs"&gt;LinkedIn&lt;/a&gt;
</code></pre>
<p>Not a single line of JavaScript required.</p>
<p>Of course this technique does have some downsides, the first is that you don't have access to things like share counts and features like Facebook showing you if your friends have liked an article.</p>
<p>The second is that you can't get them in a nice pop-up or expanding box like you can with JavaScript, you can just send them to a page.</p>
<p>Both of these things I am fine with, and other issues like not being able to track clicks onto them are easily mitigated with some JavaScript feeding into your analytics package.</p>
<p>There is also an added bonus in that you don't need to have Facebook/Twitter/Etc cookies coming from your website.</p>
<p>If you want to see the icons in action you can view the website I am working on, which is <a href="http://digitalcreativejobs.com">a Job Board for Northern Irish Digital, Creative types</a>.</p>
<p><sup>*</sup>Thanks to <a href="https://twitter.com/derekjohnson">Derek</a> for the feedback.</p>
<p>You can discuss this post on <a href="http://www.reddit.com/r/webdev/comments/165b8p/replacing_social_media_share_buttons_with/">Reddit</a> or <a href="http://news.ycombinator.com/item?id=5023817">Hacker News</a> if you like, or <a title="Quick email tip if you need to clear out your inbox" href="https://twitter.com/tosbourn">tweet me</a>.</p>
