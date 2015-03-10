---
layout: post
status: publish
published: true
title: Disable a button component with Ember
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1919
wordpress_url: http://tosbourn.com/?p=1919
date: '2014-05-28 14:36:31 +0100'
date_gmt: '2014-05-28 13:36:31 +0100'
categories:
- Development Help
tags:
- Ember
- Component
- Ember-Cli
comments: []
---
<p><em>This article is referring to Ember 1.5.1, if you are on a newer or older version this might not apply.</em></p>
<p>I want to share some code that I have written when making a component that needs to enable/disable a button in realtime.</p>
<p>This is Ember's strongsuit, but it took me some searching and playing about to get the right solution, so hopefully this helps someone else.</p>
<p>I am using Ember-CLI to build the Ember application, so some of the export syntax might not be immediately understandable but I will explain as I go along.</p>
<p>The problem is that I want a box people could compose a tweet in and I want this to be available pretty much anywhere in my application. Because of these requirements it makes perfect sense that the view side of things should be handled by a component and the controller side by a mixin.</p>
<p>I have removed a lot of code to help me make my point, so sorry if you were looking for a copy/paste twitter box solution!</p>
<p>First up I will show you my mixin <em>app/mixins/tweet-controller.js</em></p>
<pre><code>    export default Ember.Mixin.create({
    tweetContent: 'Write your tweet here',
    buttonText: "Post to Twitter",
 
    invalidTweet: function() {
      return !(this.get('tweetContent').length &lt;= 140);
    }.property('tweetContent')
 
  });
</code></pre>
<p>So this mixin will decorate any controller that uses it with some extra information, the strings at the top are used for adding some text to the component we are making, you can also see we have an invalidTweet function, which will tell us if the tweet is invalid or not, this looks at the property 'tweetContent' which is the text of our tweet.</p>
<p>I have called my main component make-a-tweet.js, this doesn't have anything relevant to our needs in it but it does mean that the component call is; <code>{%raw%}{{make-a-tweet tweetContent=tweetContent buttonText=buttonText invalidTweet=invalidTweet}}{%endraw%}</code> note that I have passed all the controller options into it.</p>
<p>The template for my component is found at <em>app/templates/components/make-a-tweet.hbs</em></p>
    {% raw %}
    {{textarea value=tweetContent}}
    {{twitter-button buttonText=buttonText disabled=invalidTweet}}
    {% endraw %}
<p>As you can see I have used Ember's built in textarea component for the textarea but I have made my own custom sub-component for the button and importantly here I am passing in <code>disabled=invalidTweet</code> this will be used in our component, which you can see I have called twitter-button so it lives at <em>app/components/twitter-button.js</em></p>
<pre><code>  export default Ember.Component.extend({
    tagName: ['button'],
 
    attributeBindings: ['disabled'],
 
    didInsertElement: function() {
      this.$().text(this.get('buttonText'));
    },
  });
</code></pre>
<p>Here I am telling the component that it is a button, and importantly for our purposes I have set <code>attributeBindings: ['disabled']</code>. What this will do is update the generated HTML with disabled= and then the value of whatever invalidTweet is. Because invalidTweet cares about changes to tweetContent, when it changes it will update.</p>
