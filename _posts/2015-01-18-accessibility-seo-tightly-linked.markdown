---
layout: post
status: publish
published: true
title: Accessibility and SEO are tightly linked
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2484
wordpress_url: http://tosbourn.com/?p=2484
date: '2015-01-18 15:51:32 +0000'
date_gmt: '2015-01-18 14:51:32 +0000'
categories:
- Development Help
tags:
- SEO
- Accessibility
- '365'
comments: []
---
<p>It is interesting that making a website accessible is often left to the last iteration of design before 'go live'. This is a bad idea and something I <a title="Review: A Web for Everyone: Designing Accessible User Experiences" href="http://tosbourn.com/review-web-everyone-designing-accessible-user-experiences/">briefly mentioned during a recent book review</a>.</p>
<p>SEO is also something that is left until the very end of the process, normally after go live when people start to notice that their site isn't number 1 in Google for "generic, highly sought after term".</p>
<p>It is a shame because both of these things are very important for very different reasons and crucially a lot of the things you will do to try and make your site accessible will also help with SEO and a lot of the stuff you do for SEO will help to make your site accessible.</p>
<p>There are two main reasons for this.</p>
<h2>Both practices require you to think of your user first and foremost</h2>
<p>Answering questions like "Would someone without prior knowledge understand this section", "Does this menu layout make sense",  and "Will someone know where this link is taking them" will help make your site accessible because you are thinking about how <strong>people</strong> are going to access your site.</p>
<p>It is going to make your site more SEO friendly because these are the types of things search engines care about, that is keywords, site structure, and anchor text.</p>
<h2>Both practices ensure your code helps to explain the content</h2>
<p>Following good technical practices like ensuring you are using the correct elements to present your data to the browser and adding supplementary information when the element alone isn't enough will make your site more accessible because assistive technologies can role with these and help present your site to your user in the best possible way for them.</p>
<p>It is going to make your site more SEO friendly because this type of rich data can really help add context to your content. If you mark up your pages correctly then search engines have a much easier time categorising and presenting that information to their users.</p>
<h2>Specific examples of SEO and Accessibility walking hand in hand</h2>
<p>Here are some specific examples of what typically is talked about in one camp or another but actually applies to both.</p>
<h3>Alt Tags</h3>
<p>I heard first about alt tags as an accessibility tool because they describe an image to someone who cannot see or understand the image.</p>
<p>Crucially machines also have a hard time understanding images, so describing them really helps search engines out when understanding what all the content on your page is talking about.</p>
<p>This also means that images that are purely decorative shouldn't have alt tags, this means screen reading software won't attempt to read them out and search engines won't care about them (win win).</p>
<h3>Text Equivalents</h3>
<p>Building on the alt tag theme is the fact that if you have say an audio file on your page common accessibility thinking would be you should have a transcript of the audio available for folk who can't hear, or are using a device that can't play audio.</p>
<p>Search engines also can't hear very well and often people will remember snippets that someone has said but not the contextual keywords. A transcript is easily read and indexed by search engines and will help people find your site.</p>
<h3>Using clear language</h3>
<p>Describing things in their simplest form and writing in a way that is easy to read is a massive accessibility win. The language you are writing in may not be the readers first language, they may have a disability which makes reading hard or maybe they are on a device which isn't really designed for reading.</p>
<p>When people search for things they normally try and search using clear and simple terms, if you are writing in those terms there is a good chance you are going to be ranked highly for them.</p>
<h3>Don't use CSS to present content or meaning</h3>
<p>This means it doesn't matter if you like the style of your H3, you should only ever use it when you are actually describing a third level heading. It also means that you don't just colour a deleted bit of content red, you mark it up as such.</p>
<p>Keyboard users who skip between headings will thank you as will colourblind users. Of course so will search engines because they don't care about CSS they just care about the markup on your page.</p>
<h3>Making sure URLs are readable and logical</h3>
<p>I had always considered this to be a purely SEO driven decision because search engines care so much about the content that resides in the URL.</p>
<p>The accessibility win is that a clearly laid out URL is better for everyone. If someone can look at your URL and deduce the content of the page they are going to feel happier about clicking on it and more sure of their decision.</p>
<h2>Wrapping up</h2>
<p>Hopefully you agree with me that a good deal of what is good for SEO benefits accessibility and what is good for accessible design is good for SEO.</p>
<p>If you want to read more about my thoughts on SEO for developers, I recently wrote about <a href="https://www.polemicdigital.com/2015/01/every-web-developer-know-seo/">what every web developers should now about SEO</a>, it touches on a lot of the points I have raised here.</p>
<p>You should also take time to read the<a href="http://www.w3.org/TR/WAI-WEBCONTENT/"> W3C Web content guidelines</a>, this is where I got most of my accessibility points from.</p>
