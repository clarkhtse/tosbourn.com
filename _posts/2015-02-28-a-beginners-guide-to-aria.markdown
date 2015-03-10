---
layout: post
status: publish
published: true
title: A beginners guide to ARIA
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2573
wordpress_url: http://tosbourn.com/?p=2573
date: '2015-02-28 18:48:32 +0000'
date_gmt: '2015-02-28 17:48:32 +0000'
categories:
- Development Help
tags:
- Accessibility
- ARIA
comments: []
---
<p>I recently talked about some <a href="http://tosbourn.com/quick-semantic-wins/" title="Quick Semantic Wins">quick semantic wins</a> and mentioned a small handful of ARIA roles you could add by default just to get the ball rolling. I wanted to expand on that point some, and while this post isn't meant to be an all encompassing resource for all things ARIA it should help you on the path to understanding it a bit more.</p>
<h2>What is ARIA</h2>
<p>I really like <a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA">Mozilla's definition of what ARIA</a> is</p>
<blockquote>
<p>Accessible Rich Internet Applications <strong>(ARIA)</strong> defines ways to make Web content and Web applications (especially those developed with Ajax and JavaScript) more accessible to people with disabilities. For example, ARIA enables accessible navigation landmarks, JavaScript widgets, form hints and error messages, live content updates, and more. ARIA is a set of special accessibility attributes which can be added to any markup, but is especially suited to HTML. The <code>role</code> attribute defines what the general type of object is (such as an article, alert, or slider).<br />
  Additional ARIA attributes provide other useful properties, such as a description for a form or the current value of a progressbar.</p>
</blockquote>
<p>The gist is that we aren't talking about marking up a blog post – that can be handled by things like <a href="http://schema.org">Schema.org</a>. </p>
<p>ARIA's main goal is to make internet applications more accessible, so things like <a href="https://twitter.com/tosbourn">Twitter</a>, <a href="https://facebook.com/thefootytipster">Facebook</a>, and <a href="https://nuu.in">Nuu</a>. With these type of websites elements are expanding/contracting, coming in and out of focus and disappearing or being created on the fly constantly. These interactions create some unique challenges for people who rely on assistive technologies.  </p>
<h2>What does ARIA look like</h2>
<p>ARIA looks like a set of attributes you add to already existing elements on the page, for example here we see the role attribute being used;</p>
<pre><code>&lt;form role="search"&gt;
  &lt;input type="text" name="search_field" /&gt;
&lt;/form&gt;
</code></pre>
<h2>Is it just defining roles?</h2>
<p>Defining roles is a massive part of the idea behind ARIA but it certainly isn't the only thing they are good for. In the following example we will see an element that can sometimes be hidden being used;</p>
<pre><code>&lt;li aria-hidden="true"&gt;Hidden&lt;/li&gt;
</code></pre>
<p>When we decide to show this <code>&lt;li&gt;</code> we would change the <code>aria-hidden</code> attribute to true, this is way more semantic that using a class <code>.hide</code> because that class could be doing anything under the hood.</p>
<h2>ARIA states</h2>
<p>The <code>aria-hidden</code> attribute is known as a state. States describe what the status is of a given element, you can imagine as state to be the answer an element would answer to a question, for example "Hey input field, are you good for me to let the user continue on with this form?", "No – I am invalid".</p>
<p>There are some element specific states, but here are the global ARIA states</p>
<ul>
<li>aria-busy </li>
<li>aria-disabled </li>
<li>aria-grabbed </li>
<li>aria-hidden </li>
<li>aria-invalid</li>
</ul>
<h2>ARIA properties</h2>
<p>As well as these states we have what are known as ARIA properties. A property is some meta data associated with an element.</p>
<p>There are some element specific properties, but to keep things simple here are the global ARIA properties</p>
<ul>
<li>aria-atomic</li>
<li>aria-controls</li>
<li>aria-describedby</li>
<li>aria-dropeffect</li>
<li>aria-flowto</li>
<li>aria-haspopup</li>
<li>aria-label</li>
<li>aria-labelledby</li>
<li>aria-live</li>
<li>aria-owns</li>
<li>aria-relevant</li>
</ul>
<p><code>aria-controls</code>, for example describes the elements whose very presence or at the very least their contents are controlled by the element you are marking up.</p>
<p>You can see how this could quickly start to add some really detailed information into your application.</p>
<h2>Hopefully this has helped</h2>
<p>This was only designed to be a very quick introductory guide to what ARIA is, hopefully I have helped ease you in and you now know enough to be dangerous!</p>
