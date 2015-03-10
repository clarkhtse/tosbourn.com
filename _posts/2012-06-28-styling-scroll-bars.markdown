---
layout: post
status: publish
published: true
title: Styling Scroll Bars
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1062
wordpress_url: http://tosbourn.com/?p=1062
date: '2012-06-28 09:51:32 +0100'
date_gmt: '2012-06-28 08:51:32 +0100'
categories:
- Development Help
tags:
- Design
- CSS
- JavaScript
- Browsers
- Scroll Bar
- Hack
comments:
- id: 151
  author: Matt Thommes
  author_email: matthom@gmail.com
  author_url: ''
  date: '2012-06-28 18:24:00 +0100'
  date_gmt: '2012-06-28 17:24:00 +0100'
  content: |-
    Perfect context, because as I was reading this in Google Reader I noticed the styled scrollbars (I have noticed it before, but this post made me look closer).

    http://media.matthom.com/images/e635ed9d223f278ef93883734aed26f6.png
---
<p>Recently I was working on a project at my job at <a title="Pierce Communications" href="http://www.piercecommunications.co.uk">Pierce Communications</a> and decided I wanted to play about with some scroll bar functionality.</p>
<p>Normally we would never advocate changing default browser behaviour — it can confuse users and jar the user experience, but occassionally small changes can be fun and add to an experience.</p>
<p>One such change is to style the scroll bars that appear when you have overflow in your content. By default the scroll bar will appear just as the browser intended, this is because the scroll bar is part of the browser's chrome, fortunately we can hack around this in most cases.</p>
<p>The first thing a lot of people would do is start looking for a jQuery plugin, and indeed there are a few out there which seem to work quite well. But I have a problem with using JavaScript for style when I shouldn't need to and I have a big problem with introducing extra code to support just to add some visual fluff. If the design really <em>really</em> needed it then I would look at using a plugin, but for a little bit of visual sugar I don't think it is worth it.</p>
<p>Of course even if we use a plugin, we shouldn't rely on JavaScript to do our dirty work, so there are also some CSS hacks we can apply, unfortunately they only work on a small amount of browsers but since this is essentially a bit of visual icing that is fine.</p>
<p>The CSS you need would be something like this;</p>
<pre>	/**
	 * This will work for some verions of Internet Explorer
	 * and apparently Opera, although I cannot confirm this.
	 */

	.myCoolDiv {
	    scrollbar-face-color: #000000;
	    scrollbar-shadow-color: #000000;
	    scrollbar-highlight-color:#000000;
	    scrollbar-3dlight-color: #000000;
	    scrollbar-darkshadow-color: #000000;
	    scrollbar-track-color: #D9D1AC;
	    scrollbar-arrow-color: #D9D1AC;
	}

	/**
	 * These will work for some versions of Webkit enabled browsers.
	 */

	.myCoolDiv::-webkit-scrollbar {
	    width: 12px;
	}

	.myCoolDiv::-webkit-scrollbar-track {
	    -webkit-box-shadow: inset 0 0 6px rgba(217, 209, 172, 0.85);
	    border-radius: 10px;
	}

	.myCoolDiv::-webkit-scrollbar-thumb {
	    border-radius: 10px;
	    -webkit-box-shadow: inset 0 0 6px rgba(217, 209, 172, 0.85);
	}</pre>
<p>There is plenty of information available online about each of the properties for both <a title="Custom Scrollbars in Internet Explorer" href="http://stackoverflow.com/questions/7725652/css-scrollbar-style-cross-browser">Internet Explorer</a> and <a title="Custom Scrollbars in Webkit" href="http://css-tricks.com/custom-scrollbars-in-webkit/">Webkit</a>.</p>
<p>Remember that with great power comes great responsibility, this should always be used with caution and always with the user experience in mind, colouring in scrollbars for the sake of it is not something we would ever do or recommend anyone do.</p>
<p>With that said, happy hacking!</p>
