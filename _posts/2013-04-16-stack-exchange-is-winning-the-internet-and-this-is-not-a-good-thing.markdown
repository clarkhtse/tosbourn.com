---
layout: post
status: publish
published: true
title: Stack Exchange is winning the internet and this is not a good thing
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1439
wordpress_url: http://tosbourn.com/?p=1439
date: '2013-04-16 20:33:32 +0100'
date_gmt: '2013-04-16 19:33:32 +0100'
categories:
- Other
tags:
- Google
- Stack Exchange
comments: []
---
<p>I have blogged about how much I like the <a title="Getting the most out of StackExchange" href="http://tosbourn.com/2010/10/web-stuff/getting-the-most-out-of-stackexchange/">Stack Exchange</a> sites in the past and my opinions on their usefulness haven't changed one bit, but I am noticing a trend that I wanted to discuss briefly.</p>
<p>Lets say I am new to a programming language and I want to know how to concatenate two strings, time was that the canonical result from a Google search would probably be a link to some spec documents or some general advice around the language. This isn't the case anymore, now you often get a Stack Overflow answer as your first result.</p>
<p>I just tried this by searching the following term: "concatenate strings in go"</p>
<p>[caption id="attachment_1440" align="aligncenter" width="578"]<a href="http://tosbourn.com/wp-content/uploads/2013/04/Screen-Shot-2013-04-16-at-19.24.25.png"><img class="size-full wp-image-1440" src="http://tosbourn.com/wp-content/uploads/2013/04/Screen-Shot-2013-04-16-at-19.24.25.png" alt="Concatenate Strings in Go" width="578" height="452" /></a> Concatenate Strings in Go[/caption]</p>
<p>The first three results from my search (I say my search because Google weights each search individually to the user making the search) all point to Stack Overflow, interestingly the second result is actually pointing to a Ruby answer, which is weird but it highlights the strength of Stack Overflow answers on the Google search index. This is why I have said they are winning the internet.</p>
<p>Why I don't think this is a good thing is because whilst for someone who is already happy with the language and has a very specific question this is excellent, but in the case of needing to concatenate two strings we can infer that the user probably doesn't have much of a background in the language and I don't think this straight to the point question and answer setup is the best for this person.</p>
<p>The question they find will more often than not talk about an edge case where the first answer might be best suited to that edge case but perhaps not best suited as a general rule of thumb, and indeed other answers that are perfectly valid in a general case may be voted down in this specific case and a rookie user will probably not pick up on that.</p>
<p>The fact that Stack Exchange answers appear so high in search results often means as well that people assume that if it isn't on the Stack Exchange they should ask it, which leads to too many questions being asked that could be answered by reading the manual or doing a tiny bit of experimentation.</p>
<p><strong>This extremely efficient mechanism for finding out the exact answer to your question is creating a generation of very efficient, but perhaps not entirely well rounded developers who can churn out code very quickly but perhaps don't understand the code as well as they should.</strong></p>
<p>I should point out, this is in no way the fault of Stack Overflow, they are providing an excellent service and they are clearly doing their fair share of Search Engine Optimising to be able to achieve such results, I think that if any physical thing is at fault here it is maybe Google, they are charged with finding people the most relevant result and whilst on paper an exact match between your query and a Stack Overflow question should result in Stack Overflow being the canonical link, I am not sure it is the most relevant link in practice.</p>
<p>To be honest to call Google at fault is probably clutching at straws, the real issue I think is that too many developers are happy to dive in and ask someone to do their thinking for them before properly trying to solve the issue themselves, I don't know how we fix that.</p>
<p>By the way, here is the best way to concatenate strings in Go, via Stack Overflow of course :-)</p>
<pre><code>package main
import "bytes"
func main() {
    var buffer bytes.Buffer
    for i := 0; i &lt; 1000; i++ {
        buffer.WriteString("a")
    }
    println(buffer.String())
}</code></pre>
<p>If you want to discuss this you can hit me up on <a href="https://www.twitter.com/tosbourn">Twitter</a>, or there are <a href="http://www.reddit.com/r/webdev/comments/1chbhk/stack_exchange_is_winning_the_internet_and_this/">Reddit</a> and <a href="https://news.ycombinator.com/item?id=5560300">Hacker News</a> threads.</p>
<p>I spoke to Jeff Atwood on Twitter about it and this was his response:</p>
<blockquote class="twitter-tweet"><p>@<a href="https://twitter.com/tosbourn">tosbourn</a> this is an old debate, "go read the whole book first" versus "answer my specific question". Good devs will seek background.</p>
<p>— Jeff Atwood (@codinghorror) <a href="https://twitter.com/codinghorror/status/324248915488673792">April 16, 2013</a></p></blockquote>
<p>Joel Spolsky also got back to me about it:</p>
<blockquote class="twitter-tweet"><p>@<a href="https://twitter.com/tosbourn">tosbourn</a> @<a href="https://twitter.com/codinghorror">codinghorror</a> devs page-fault in the minimum knowledge to get the job done</p>
<p>— Joel Spolsky (@spolsky) <a href="https://twitter.com/spolsky/status/324263465239851008">April 16, 2013</a></p></blockquote>
