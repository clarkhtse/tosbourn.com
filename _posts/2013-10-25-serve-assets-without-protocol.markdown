---
layout: post
status: publish
published: true
title: You should serve up assets without a protocol
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1712
wordpress_url: http://tosbourn.com/?p=1712
date: '2013-10-25 18:32:58 +0100'
date_gmt: '2013-10-25 17:32:58 +0100'
categories:
- Development Help
tags:
- html
- Protocols
- Assets
- Loading
- HTTP
- HTTPS
comments:
- id: 241
  author: Max Morgan
  author_email: max@maxmorgandesign.com
  author_url: ''
  date: '2013-10-25 18:49:00 +0100'
  date_gmt: '2013-10-25 17:49:00 +0100'
  content: It's worth noting that if you are still supporting IE7/8, it tends to download
    stylesheets twice when included on the page using a protocol-less URL.
- id: 242
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-25 18:55:00 +0100'
  date_gmt: '2013-10-25 17:55:00 +0100'
  content: Thanks for this Max, I have updated the post to reflect this!
- id: 243
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-25 18:59:00 +0100'
  date_gmt: '2013-10-25 17:59:00 +0100'
  content: Thanks for this Max! I have updated the blog post.
- id: 244
  author: Zach Lysobey
  author_email: zlysobey@gmail.com
  author_url: ''
  date: '2013-10-25 22:50:00 +0100'
  date_gmt: '2013-10-25 21:50:00 +0100'
  content: Also worth noting that this protocol-agnostic approach requires you serve
    your web-page through a web-server. In other words, if you try to open a .html
    file from the Desktop, it will use file:// rather than http(s):// which will cause
    problems.
- id: 246
  author: kryptogoloc
  author_email: kryptogoloc@hotmail.com
  author_url: ''
  date: '2013-10-26 01:17:00 +0100'
  date_gmt: '2013-10-26 00:17:00 +0100'
  content: Any developer who doesn't know how to use the ambient scheme is not really
    a developer ... oh wait they are web developers.
- id: 247
  author: Gav
  author_email: gavin+1232@gav-roberts.co.uk
  author_url: ''
  date: '2013-10-26 10:13:00 +0100'
  date_gmt: '2013-10-26 09:13:00 +0100'
  content: Was the hex code appended to the good image intentional?
- id: 248
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-26 11:14:00 +0100'
  date_gmt: '2013-10-26 10:14:00 +0100'
  content: |-
    Good spot, it wasn't, it looks like maybe something WordPress was doing, basically every time I put a file extension in it was adding it, super weird.

    I had checked for whitespace characters or anything like that - I might investigate this more when I have time, but for now, thanks again for the spot!
- id: 249
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-26 11:14:00 +0100'
  date_gmt: '2013-10-26 10:14:00 +0100'
  content: A fair point Zach and thanks for bringing it up. I am about to update the
    blog to reflect this.
- id: 250
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-26 11:20:00 +0100'
  date_gmt: '2013-10-26 10:20:00 +0100'
  content: "Thanks for your comment.\n\nCould you explain to me what an ambient scheme
    is? \n\nI searched online but couldn't find any references to this term."
- id: 493
  author: JDM
  author_email: jdmensing@gmail.com
  author_url: ''
  date: '2014-06-02 17:16:00 +0100'
  date_gmt: '2014-06-02 16:16:00 +0100'
  content: No, apparently he can't.  I was also interested in researching this mystical
    "ambient scheme" after reading his comment.  Appears to be a construct of his
    universe used to deride those who are less enlightened.
---
<p>Something that recently bit us at <a href="https://examtime.com">ExamTime</a> when we were doing some work that involved proxies and other "thar be dragons" stuff was how after applying some domain changes we would oftentimes get mixed content warnings because we were loading <code>http://</code> assets onto an <code>https://</code> domain.</p>
<p>Some browsers handle this news better than others, and because we cannot say for sure how every browser will react, we needed to stop this from happening.</p>
<p>Normally a website can get around mixed content warnings by making a call and doing sweeping changes - an all or nothing sort of approach, this wouldn't work for us for our scenario and in the future it might not work for you, so the following technique is something I think all developers should have in their arsenal.</p>
<p>The solution is a simple one - assets on your site should be loaded without an attached protocol, for example;</p>
<pre><code>&lt;img src="http://bad.com/bad.jpg" /&gt;</code></pre>
<p>Should really be</p>
<pre><code>&lt;img src="//good.com/good&#46;jpg" /&gt;</code></pre>
<p>So, what does this do and what does this afford you?</p>
<p>Basically if you load an asset (and by asset I mean things like, images, CSS files, JavaScript files) without a protocol (the <code>http:</code> bit) then the browser will decide which protocol to use, and the protocol it will decide to use is the one that the main page is being loaded with.</p>
<p>This means that if someone visits https://yoursite.com all assets will come over https too, which is good for avoiding mixed content warnings.</p>
<p>I have been made aware of one potential downside from a very kind commenter, if you still support IE7 or IE8 then it can download stylesheets twice if no protocol is used. That kind of sucks, but I don't actively support older browsers so I am happy for them to talk a small performance hit.</p>
<p>Another (equally kind) commenter points out that if you are running your files totally locally (using file://) then this will be the protocol adopted throughout, which depending on the rest of your setup might cause problems.</p>
<p>Another issue which I have forgotten to mention but it was brought up in a Reddit comment was that if you are linking to a third party website and you use this method and you send through http traffic but they only support https traffic then you could find yourself with issues, a quick test before you change to // should tell you if this is going to be the case or not.</p>
