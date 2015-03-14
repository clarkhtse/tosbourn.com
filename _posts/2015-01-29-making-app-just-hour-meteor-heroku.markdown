---
layout: post
status: publish
published: true
title: Making an app in just over an hour with Meteor and Heroku
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2509
wordpress_url: http://tosbourn.com/?p=2509
date: '2015-01-29 23:09:46 +0000'
date_gmt: '2015-01-29 22:09:46 +0000'
categories:
- Development Help
tags:
- Meteor
- getUserMedia
- Working Wall
comments:
- id: 688
  author: Aaron Pollock
  author_email: aaron@aarpol.com
  author_url: ''
  date: '2015-01-30 17:20:00 +0000'
  date_gmt: '2015-01-30 16:20:00 +0000'
  content: "Nice demo. Tried it in Safari first, got an exception. \nhttp://d.pr/i/iNwI/1TL8vc8X\n\n\nThen
    realised that it's not supported there yet.\nhttp://caniuse.com/#search=getusermedia\n\n\nThat's
    browsers for you."
- id: 689
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2015-01-30 17:35:00 +0000'
  date_gmt: '2015-01-30 16:35:00 +0000'
  content: heh aye! Cheers. Got a few bug fixes I want to do (like when a browser
    isn't supported handle that nicely)
---
<p>Yesterday I thought up a fun idea for an app that would help me learn a bit about the <a href="http://www.html5rocks.com/en/tutorials/getusermedia/intro/">media capture APIs</a> available in HTML5. I also wanted to finish an end to end <a href="https://www.meteor.com">Meteor</a> application as I have only really followed tutorials before or worked on something along with other developers.</p>
<p>I was able to create and launch the app in just over an hour. So you can say hello to <a href="http://working-wall.herokuapp.com">Working Wall</a>.</p>
<p>[caption id="attachment_2513" align="aligncenter" width="300"]<a href="http://tosbourn.com/wp-content/uploads/2015/01/Screenshot-2015-01-29-22.11.31.png"><img class="size-medium wp-image-2513" src="http://tosbourn.com/wp-content/uploads/2015/01/Screenshot-2015-01-29-22.11.31-300x130.png" alt="Screenshot of Working Wall" width="300" height="130" /></a> Screenshot of Working Wall</p>
<p>I take absolutely no credit for being able to get something up and running this fast, it was all thanks to Meteor and Heroku. I wanted to walk you through my process to show how easy it is.</p>
<p>I am going to assume you have both Meteor installed and a Heroku account, both are free and easy to set up. I don't mention them here purely to keep this post as neat as possible.</p>
<h2>Meteor</h2>
<p>I created the app with a simple Meteor call, this sets up some really basic boiler plate.</p>
<p><code>meteor create working-wall</code></p>
<p>Next up I edited the three files that were created called <code>working-wall.css</code>, <code>working-wall.html</code>, and <code>working-wall.js</code>.</p>
<p>The CSS is for the styling, the HTML is for the templating and the JS is for the actual Mongo workings. Here are my completed HTML and JS files (at the time of writing, there are some bugs to fix and improvements to make that may have happened by the time you read this).</p>
<p>Disclaimer: This isn't production ready code, I haven't put a thought to security or testing, I just wanted something up that I could play with.</p>
<p>working-wall.html</p>
<pre><code>
{% raw %}
&lt;head&gt;
  &lt;title&gt;Working Wall&lt;/title&gt;
&lt;/head&gt;

&lt;body&gt;
  &lt;header&gt;
    &lt;h1&gt;Here are some folk working on interesting stuff!&lt;/h1&gt;
    &lt;p&gt;Or maybe just some cats&amp;hellip;&lt;/p&gt;
    &lt;p&gt;Accept the request to use your camera. Click on your picture to take a snapshot&lt;/p&gt;
  &lt;/header&gt;
  {{&gt; pictures}}
  &lt;footer&gt;
    Made by &lt;a href="http://twitter.com/tosbourn"&gt;Toby&lt;/a&gt; | Inspired by &lt;a href="http://www.tiiny.com"&gt;Tiiny&lt;/a&gt; | &lt;a href="https://github.com/tosbourn/working-wall"&gt;Source Code&lt;/a&gt;
  &lt;/footer&gt;
&lt;/body&gt;

&lt;template name="pictures"&gt;
  &lt;ul&gt;
    &lt;li class="main-picture"&gt;
    &lt;video autoplay height="150px"&gt;&lt;/video&gt;
    &lt;canvas style="display:none;"&gt;&lt;/canvas&gt;
    &lt;/li&gt;
    {{#each pictures}}
      &lt;li&gt;&lt;img src="{{url}}" /&gt;&lt;/li&gt;
    {{/each}}
  &lt;/ul&gt;
&lt;/template&gt;
{%endraw%}
</code></pre>
<p>Nothing too exciting, the HTML at the top sets a header and footer and calls the template named pictures. All this template does is set up the "webcam" area and loop through all the pictures displaying them.</p>
<pre><code>Pictures = new Mongo.Collection("pictures");

if (Meteor.isClient) {

 Template.pictures.helpers({
 pictures: function () {
 return Pictures.find({}, {sort: {'date_added': -1}, limit: 50});
 }
 });

 Template.pictures.rendered = function() {
 var video = document.querySelector('video');
 var canvas = document.querySelector('canvas');
 var ctx = canvas.getContext('2d');
 var localMediaStream = null;

 function snapshot() {
 if (localMediaStream) {
 ctx.drawImage(video, 0, 0, 400, 150);
 Pictures.insert({url: canvas.toDataURL('image/png'), date_added: new Date});
 video.src = window.URL.createObjectURL(localMediaStream);
 }
 }

 video.addEventListener('click', snapshot, false);

 navigator.getUserMedia = navigator.getUserMedia ||
 navigator.webkitGetUserMedia ||
 navigator.mozGetUserMedia ||
 navigator.msGetUserMedia;

 navigator.getUserMedia({video: true}, function(stream) {
 video.src = window.URL.createObjectURL(stream);
 localMediaStream = stream;
 }, function(){
 console.log("error getting image");
 });
 }
}

if (Meteor.isServer) {
 Meteor.startup(function () {});
}</code></pre>
<p>This is a little more interesting;</p>
<p>We set up a new collection called Pictures.</p>
<p>Next we check if we are in the client or the server. If we are in the client set up a helper called pictures – this is what we iterate over in the template. It is doing a grab of the latest 50 images sorted descending by date.</p>
<p>This next part is a bit ugly and could definitely be refactored, we are saying when the pictures template is rendered run the following JavaScript, this sets up the browser asking the user to give us access to the webcam and then looks for a click on the video element, once clicked it captures the current frame into a canvas and then converts that into raw png data.</p>
<p>I did experiment with creating webp images, these were a lot smaller but didn't render on every browser.</p>
<p>Meteor handles storing the information with this line;</p>
<pre><code>Pictures.insert({url: canvas.toDataURL('image/png'), date_added: new Date});</code></pre>
<p>That is really all there is to it, Meteor handles creating the Mongo database and handling the collection we have asked for.</p>
<h2>Heroku</h2>
<p>Getting into Heroku was as simple as setting up a build pack, there are several available but I chose to use <a href="https://github.com/AdmitHub/meteor-buildpack-horse.git">meteor-buildpack-horse.git</a>. I wish I could say this was an educated choice, but it was what I know <a href="https://twitter.com/overture8">Phil McClure</a> has used in the past and I trust his judgement on all Meteor matters! (sidenote: he has written some great stuff about Meteor on <a href="http://notions.me">his blog</a>).</p>
<p>I also had to set up a free plan on MongoLab to handle the database, once this was setup the URL can be used by your buildpack to set everything up. Way more simple than I imagined.</p>
<h2>Conclusion</h2>
<p>This was very much a quick sprint through what I did, I will be expanding some of the points and things in other posts in the future, if there is anything in particular you want to ask about let me know in the comments.</p>
