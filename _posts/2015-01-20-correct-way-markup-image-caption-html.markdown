---
layout: post
status: publish
published: true
title: The correct way to markup an image and caption in HTML
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2500
wordpress_url: http://tosbourn.com/?p=2500
date: '2015-01-20 20:22:19 +0000'
date_gmt: '2015-01-20 19:22:19 +0000'
categories:
- Development Help
tags:
- Semantics
- '365'
- Figure
- Figcaption
comments: []
---
<p>I my recent post about <a title="Quick Semantic Wins" href="http://tosbourn.com/quick-semantic-wins/">quick semantic wins</a> I mentioned that captioning an image should be done with <code>&lt;figure&gt;</code> and <code>&lt;figcaption&gt;</code></p>
<p>I wanted to explain it in a bit more detail with a quick example.</p>
<pre><code>&lt;figure&gt;
 &lt;img src="http://placekitten.com/200/300" alt="Small picture of a kitten" /&gt;
 &lt;figcaption&gt;
 Small picture of a kitten, graciously shared by &lt;a href="http://placekitten.com"&gt;placekitten.com&lt;/a&gt;
 &lt;/figcaption&gt;
&lt;/figure&gt;
</code></pre>
<p>Here is a <a href="https://gist.github.com/tosbourn/bf20e0a6d122b5b89643">gist of it</a>, if you like that sort of thing!</p>
<p>So what we have is a <code>&lt;figure&gt;</code> element which holds both an <code>&lt;img&gt;</code> and a <code>&lt;figcaption&gt;</code> element.</p>
<p>The implied meaning here is that the contents of <code>&lt;figcaption&gt;</code> caption the rest of the contents of <code>&lt;figure&gt;</code> which in this case is an <code>&lt;img&gt;</code>, but it could have been a video file or tabular information – anything that constitutes something that could be captioned really.</p>
<p>The other thing you may notice is that I have included a link inside <code>&lt;figcaption&gt;</code>, this is because <code>&lt;figcaption&gt;</code> is a block level element and can have elements inside itself. As well as links a common thing you might find would be <code>&lt;cite&gt;</code>.</p>
<p>I was happy to note that WordPress gets this right out of the box. I have seen other CMS incorrectly use spans and divs to accomplish this but WordPress leads the way when it comes to marking up captioned images correctly!</p>
<h2>Why should I care?</h2>
<p>You might rightly wonder why you would care about correctly captioning images. There are several reasons.</p>
<ul>
<li><strong>Not all images make sense by themselves</strong> – You can't assume everyone is going to understand your image, adding a caption provides much needed context.</li>
<li><strong>More content for you</strong> – If you supplement your images with correct captions you are adding extra contextual information for your users but likewise you are adding more content for search engines to find.</li>
<li><strong>Captions can be translated by software, images can't</strong> – Which immediately opens up your images to being understood by an international audience.</li>
<li><strong>It is professional</strong> – You expect journals, books and magazines to correctly caption their images, why shouldn't people expect it from your website?</li>
</ul>
