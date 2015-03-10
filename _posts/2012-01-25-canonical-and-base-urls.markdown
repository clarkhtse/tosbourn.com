---
layout: post
status: publish
published: true
title: Canonical and Base URLs
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 809
wordpress_url: http://tosbourn.com/?p=809
date: '2012-01-25 11:30:43 +0000'
date_gmt: '2012-01-25 10:30:43 +0000'
categories:
- Development Help
tags:
- html
- Canonical
- Base
comments:
- id: 103
  author: Barry Adams
  author_email: barry.adams@gmail.com
  author_url: http://www.barryadams.co.uk/
  date: '2012-01-25 12:06:00 +0000'
  date_gmt: '2012-01-25 11:06:00 +0000'
  content: |-
    "Some people just don’t care about ranking well in search engines" - and we generally refer to these people as idiots.

    Ignoring the single most common way users find information online is, well, pretty damn stupid.

    But, hey, I'm an SEO guy so I might be biased. :)
- id: 104
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2012-01-25 13:11:00 +0000'
  date_gmt: '2012-01-25 12:11:00 +0000'
  content: I think it is pretty dumb as well, but many would see duplicate content
    issues as more than the bare minimum they think they need to do in order to have
    a web presence.
- id: 109
  author: web tasarım
  author_email: info@sibersonik.com
  author_url: http://www.sibersonik.com/
  date: '2012-02-03 18:05:00 +0000'
  date_gmt: '2012-02-03 17:05:00 +0000'
  content: honestly I care seo alot , but when dont care for seo ıc an sleep better
    :)
---
<h2>Canonical URLs</h2>
<p>According to <a href="http://en.wikipedia.org/wiki/Canonical#Computer_science" target="_blank">Wikipedia</a> the word canonical in a Computer Science sense means "the usual or standard state or manner of something", in terms of web development canonical URLs are the preferred URLs as picked by the web developer. So when a website has multiple URLs for the same content specifying a canonical URL tells search engines which link they should display to the public.</p>
<p>To use canonical URLs you should place something like the following in the head of your document;</p>
<pre>&lt;link rel="canonical" href="http://www.example.com/category/my_page.html"&gt;</pre>
<p>Unfortunately this is only a signal, not a directive - so search engines don't need to follow this, but from what I can see it appears to be a pretty strong signal.</p>
<p>What is cool is that the canonical link can point to another domain alltogther - this could be useful if you don't have access to do other forms of redirection.</p>
<h2>Base URLs</h2>
<p>Base URLs let the web developer specify a documents base URI explicity, this ties in nicely with canonical links which can be relative if you wish and can help with duplicate content issues for linked content coming from your site.</p>
<p>To use base URLs you should place something like the following in the head of your document;</p>
<pre>&lt;base href="http://www.example.com/category/my_page.html"&gt;</pre>
<p>At the first pass you are probably thinking that this is the exact same as the canonical URL we wanted to include, the difference with this is that then we do something like;</p>
<pre>&lt;img src="../img/myimg.png" alt="my test image" /&gt;</pre>
<p>And this would relate to http://example.com/img/myimg.png - pretty cool eh?</p>
<p>This will basically mean that your canonical URL can be replicated throughout relative links in your site, which improves the chances that search engines will index the URL you want them to index.</p>
<h2>I don't care about SEO - why should I do this?</h2>
<p>Some people just don't care about ranking well in search engines, and that is fine, but I still think you should look into implementing these tags were appropriate on your website - here is why.</p>
<p>I am currently working on a legacy project that is a site that accepts multiple domain names, it then uses some database magic to display different sites depending on the domain. Simple enough. The only issue is that the original developers didn't think about the need to provide a canonical URL, so b.com/a/b/c and x.com/a/b/c show the same content across different domains and unfortunately somewhere along the line Google has indexed 'b' as sitting under x.com instead of b.com - which just looks wrong (even if you don't care about rank)</p>
<p>Granted this is just an edge base, but it is one of many that can be solved by the correct application of both canonical and base urls.</p>
<h2>Further Reading:</h2>
<h3>Canonical Links</h3>
<ul>
<li><a href="http://support.google.com/webmasters/bin/answer.py?hl=en&amp;answer=139394" target="_blank">http://support.google.com/webmasters/bin/answer.py?hl=en&amp;answer=139394</a></li>
<li><a href="http://www.mattcutts.com/blog/seo-advice-url-canonicalization/" target="_blank">http://www.mattcutts.com/blog/seo-advice-url-canonicalization/</a></li>
<li><a href="http://en.wikipedia.org/wiki/URL_normalization" target="_blank">http://en.wikipedia.org/wiki/URL_normalization</a></li>
<li><a href="http://www.seomoz.org/blog/canonical-url-tag-the-most-important-advancement-in-seo-practices-since-sitemaps" target="_blank">http://www.seomoz.org/blog/canonical-url-tag-the-most-important-advancement-in-seo-practices-since-sitemaps</a></li>
</ul>
<h3>Base Links</h3>
<ul>
<li><a href="http://www.w3.org/TR/html4/struct/links.html#h-12.4" target="_blank">http://www.w3.org/TR/html4/struct/links.html#h-12.4</a></li>
</ul>
