---
layout: post
status: publish
published: true
title: Validation in CakePHP 1.3
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 867
wordpress_url: http://tosbourn.com/?p=867
date: '2012-03-13 13:30:07 +0000'
date_gmt: '2012-03-13 12:30:07 +0000'
categories:
- Development Help
tags:
- CakePHP
comments:
- id: 433
  author: bestonetechnologies.com
  author_email: admin@bestonetechnologies.com
  author_url: ''
  date: '2014-03-19 07:57:00 +0000'
  date_gmt: '2014-03-19 06:57:00 +0000'
  content: thanks, nice post
---
<p>This is such a crucial task to many apps and is something that CakePHP has made very simple - unfortunately it hasn't been documented anywhere easily accessible on the Cake site - The book splits up validation across several chapters and many of the tutorials online focus on older versions of Cake or are simply wrong.</p>
<p>Naturally then what we need is another blog post on the subject! This will explain how I perform validation in CakePHP 1.3. I am not saying this is the best way, or the only way, but it is a way that works for me.</p>
<h2>Model</h2>
<p>Because validation is essentially giving your data some meta-data to say 'This data needs to have x, y or z before I allow it to be saved' it makes sense that we need to go into the model to get everything kicked off.</p>
<p>I won't go into too much detail on the options available as these are covered in <a href="http://book.cakephp.org/1.3/en/view/1143/Data-Validation" target="_blank">the book</a>, but basically you need to put in a variable called $validate;</p>
<p><code></p>
<pre>
var $validate = array(
'name' =&gt; array(
'rule'       =&gt; 'alphaNumeric',
'required'   =&gt; true,
'allowEmpty' =&gt; false,
'message'    =&gt; 'Please enter your name'
),
'email' =&gt; array(
'rule'       =&gt; 'email',
'required'   =&gt; true,
'allowEmpty' =&gt; false,
'message'    =&gt; 'Please enter your email address'
)
);
</pre>
<p></code></p>
<p>Obviously replace the fields and rules with your own, but that is the basic idea.</p>
<h2>Controller</h2>
<p>In the controller I perform a test to see if the data is valid before saving, if it is then you save as normal, if it isn't then I append the error messages into the inbuilt flash function.</p>
<p><code></p>
<pre>
$this-&gt;Contact-&gt;set($this-&gt;data);

if ($this-&gt;Contact-&gt;validates()) {
//Normal Saving Stuff
} else {
$this-&gt;Session-&gt;setFlash(__(implode('&lt;br /&gt;', $this-&gt;Contact-&gt;invalidFields()), true));
}
</pre>
<p></code><br />
The three important things here are;</p>
<ul>
<li>Setting the data to the model</li>
<li>Doing the validates() check</li>
<li>Imploding the error array to make it a string for the setFlash function</li>
</ul>
<p>Hopefully this helps someone stuck with CakePHP validation.</p>
