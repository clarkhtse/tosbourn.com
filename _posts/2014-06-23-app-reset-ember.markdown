---
layout: post
status: publish
published: true
title: What App.reset() does in Ember
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2069
wordpress_url: http://tosbourn.com/?p=2069
date: '2014-06-23 22:17:06 +0100'
date_gmt: '2014-06-23 21:17:06 +0100'
categories:
- Development Help
tags:
- Ember
comments:
- id: 504
  author: il1019
  author_email: il10192@yahoo.com
  author_url: ''
  date: '2014-06-30 09:41:00 +0100'
  date_gmt: '2014-06-30 08:41:00 +0100'
  content: Great article, I love peeking into Ember a little deeper.
- id: 506
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-06-30 12:46:00 +0100'
  date_gmt: '2014-06-30 11:46:00 +0100'
  content: Thanks, glad you enjoyed it!
- id: 561
  author: Sean Omlor
  author_email: somlor@gmail.com
  author_url: http://seanomlor.com/
  date: '2014-08-21 02:13:00 +0100'
  date_gmt: '2014-08-21 01:13:00 +0100'
  content: Really enjoyed this dissection, thanks.
- id: 568
  author: taylor
  author_email: taylor.allred@vivint.com
  author_url: ''
  date: '2014-09-02 23:13:00 +0100'
  date_gmt: '2014-09-02 22:13:00 +0100'
  content: Great article! Loved the references and details to understand how things
    work! Thanks!!
---
<p>Earlier today I wrote a post show<a title="Using Ember’s App.reset() to kill off any local data" href="http://tosbourn.com/using-embers-app-reset-kill-local-data/"> how using <code>App.reset()</code> helped me with a caching issue</a>, at the end of it I asked if there was maybe something better I can do.</p>
<p>This evening I wanted to take  a look at what is actually going on under the hood when you call <code>App.reset();</code> in your Ember application.</p>
<p>This is going to be a bit of a live blog, where I go through line by line and work out what is happening.</p>
<p>Lets get right down to it, here is <a href="https://github.com/emberjs/ember.js/blob/v1.5.0/packages/ember-application/lib/system/application.js#L613">the code for reset</a> (as of 1.5.0);</p>
<pre><code>reset: function() {
    this._readinessDeferrals = 1;

    function handleReset() {
      var router = this.__container__.lookup('router:main');
      router.reset();

      Ember.run(this.__container__, 'destroy');

      this.buildContainer();

      Ember.run.schedule('actions', this, function() {
        this._initialize();
      });
    }

    Ember.run.join(this, handleReset);
  },</code></pre>
<p>Fairly short, but there is plenty of stuff going on that I have no idea about, to be honest I was stumped even by the first line;</p>
<pre><code>this._readinessDeferrals = 1;</code></pre>
<p>A quick search revealed <a href="http://discuss.emberjs.com/t/what-is-the-latest-with-initialization-and-deferreadiness/1074/2" target="_blank">this conversation on the Ember.js message boards</a> which talks about a <code>deferReadiness</code> function which checks for <code>this._readinessDeferrals</code> being &lt;= 0, so it looks like it is a flag to say that we are not ready just yet. You would call <code>deferReadiness</code> if you don't want your app to <a href="http://emberjs.com/api/classes/Ember.Application.html" target="_blank">initialize immediately</a>.</p>
<p>So next we create this <code>handleReset</code> function, before looking at this in much detail I already know that it performs four main tasks (<a href="http://tosbourn.com/using-embers-app-reset-kill-local-data/">from my previous post</a>). Knowing this sort of high level thing really helps when you are digging into code, so I will repost it here;</p>
<ol>
<li>Deactivate existing routes</li>
<li>Destroy all objects in the container</li>
<li>Create a new application container</li>
<li>Re-route to the existing url</li>
</ol>
<p>The first thing that happens inside this <code>handleReset</code> function is that we set up a variable called <code>router</code>;</p>
<pre><code>var router = this.__container__.lookup('router:main');</code></pre>
<p>I have seen this <code>__container__</code> variable before, but have never known what it actually corresponds to, a search brings up an <a href="https://github.com/emberjs/ember.js/commit/5becdc4467573f80a5c5dbb51d97c6b9239714a8">old commit</a> that shows that <code>__container__</code> used to be just <code>container</code> but people were using it for grabbing controllers without using the proper means. This leads me to believe that <code>__container__</code> is your main namespaced application.</p>
<p>Calling <code>.lookup</code> on it and passing in what you want is the main way you interact with <code>__container__</code>, this is covered in a fair amount of detail in <a href="http://emberjs.com/guides/understanding-ember/debugging/">Ember's debugging guide</a>.</p>
<p>Now we have the main router we call <code>.reset()</code>;</p>
<pre><code>router.reset();</code></pre>
<p>This makes sense, we are resetting the router, this is a private method <a href="http://emberjs.com/api/classes/Ember.Router.html#method_reset" target="_blank">detailed here</a>.</p>
<p>Next up it looks like we are destroying the container;</p>
<pre><code>Ember.run(this.__container__, 'destroy');</code></pre>
<p><code>Ember.run</code> runs the passed target and method inside of a RunLoop, you can <a href="http://emberjs.com/api/classes/Ember.run.html" target="_blank">read about it</a> in the Ember docs.</p>
<p>Since we have just destroyed the container, it makes sense that we want to make a new one, this is handled by;</p>
<pre><code>this.buildContainer();</code></pre>
<p>Next up we have the following block of code;</p>
<pre><code> Ember.run.schedule('actions', this, function() {
   this._initialize();
 });</code></pre>
<p>We see this <code>Ember.run</code> again and this time we are calling <code>.schedule</code> on it, I can guess at what this does but consulting this <a href="http://emberjs.com/guides/understanding-ember/run-loop/" target="_blank">really useful guide on understanding the Ember run loop</a> helps a lot. From it we can see that 'actions'  is the queue we want to add things to, this is the context we want to pass in and then the anonymous function is the thing we actually want to run.</p>
<p>Now we just need to work out what the following actually does;</p>
<pre><code>this._initialize();</code></pre>
<p>This code <a href="https://github.com/emberjs/ember.js/blob/v1.5.0/packages/ember-application/lib/system/application.js#L523" target="_blank">sits just above our reset code</a> in the Ember codebase; You can see that it goes through and initializes everything that Ember needs to function.</p>
<p>We are down to our final line;</p>
<pre><code>Ember.run.join(this, handleReset);</code></pre>
<p>Something else using the Ember run loop I see! From <a href="http://emberjs.com/api/classes/Ember.run.html#method_join" target="_blank">reading the docs</a> I can see that join will either queue itself to an existing run loop or create a new one. As normal we are passing in a context (or target as Ember calls it) of <code>this</code> and we are calling <code>handleReset</code>, our function we just created!</p>
<p>I learned a lot tonight, hope you did too! Let me know if you enjoyed this type of post in the comments, I will do more of them if they are useful.</p>
