---
layout: post
title: An experiment in highlighting words
categories:
- Experiement
tags:
- JavaScript
description: An experiement in highlighting words
---

I want to play with the idea of allow people to click on words within a sentence to be able to "highlight" those words. It will be building towards something I am working on that will allow people to have a palette of colours which they can use to signify their feelings towards certain parts of a sentence.

I figure the first thing I want to do is group my words into something and split each word out as a span element. I will also need some CSS to know when I have highlighted a word correctly or not.

    <blockquote id="highlightable">
	  <span>Here</span> <span>are</span> <span>some</span> <span>words</span> <span>I</span> <span>want</span> <span>to</span> <span>highlight</span>
    </blockquote>

    <style>
    .highlighted {
      background-color: yellow;
    }
    </style>

Which makes

<style>
	.highlighted {
	background-color: yellow;
	}
</style>

<blockquote>
    <span>Here</span> <span>are</span> <span>some</span> <span>words</span> <span>I</span> <span>want</span> <span>to</span> <span>highlight</span>
</blockquote>

Next up I want some JavaScript which recognises that I have clicked on one of these spans;

	<script>
	  function highlightText(event) {
	    event.currentTarget.className = (event.currentTarget.className === "highlighted") ? "" : "highlighted";
	  }
	  var spans = document.getElementById("highlightable").getElementsByTagName("span");
	  for(var i = 0; i < spans.length; i++) {
	    spans[i].addEventListener("click", highlightText, false);
	  }
	</script>


And here is it working so far.

<blockquote id="highlightable">
    <span>Here</span> <span>are</span> <span>some</span> <span>words</span> <span>I</span> <span>want</span> <span>to</span> <span>highlight</span>
</blockquote>

<script>
	function highlightText(event) {
		event.currentTarget.className = (event.currentTarget.className === "highlighted") ? "" : "highlighted";
	}
	var spans = document.getElementById("highlightable").getElementsByTagName("span");
	for(var i = 0; i < spans.length; i++) {
		spans[i].addEventListener("click", highlightText, false);
	}
</script>

In another blog post I will go through some thoughts on how I can make a quick colour selector for this, and also how I would go about counting / grabbing the highlighted words. I want to eventually be able to say 5 words were highlighted, and it was these words.
