---
layout: post
status: publish
published: true
title: A fix for window.location.origin in Internet Explorer
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1622
wordpress_url: http://tosbourn.com/?p=1622
date: '2013-08-15 10:39:16 +0100'
date_gmt: '2013-08-15 09:39:16 +0100'
categories:
- Development Help
tags:
- JavaScript
- Fix
- Window
comments:
- id: 232
  author: Saturate
  author_email: allankimmerjensen@gmail.com
  author_url: ''
  date: '2013-10-04 13:20:00 +0100'
  date_gmt: '2013-10-04 12:20:00 +0100'
  content: You forgot that origin includes the port number, you code does not :-)
- id: 233
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-10 01:21:00 +0100'
  date_gmt: '2013-10-10 00:21:00 +0100'
  content: Good spot! I have fixed the post, thanks!
- id: 234
  author: John
  author_email: johntnorris@outlook.com
  author_url: ''
  date: '2013-10-16 11:47:00 +0100'
  date_gmt: '2013-10-16 10:47:00 +0100'
  content: That's a life saver right there.. Thanks!
- id: 236
  author: ⓕⓣ
  author_email: folktrash@gmail.com
  author_url: ''
  date: '2013-10-17 18:36:00 +0100'
  date_gmt: '2013-10-17 17:36:00 +0100'
  content: maybe see about getting this added to modernizer or post small repro on
    github, or get onto the pollyfill radar. nice snippet.
- id: 237
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-17 22:36:00 +0100'
  date_gmt: '2013-10-17 21:36:00 +0100'
  content: 'Good idea - I have added it here: https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills#other'
- id: 238
  author: ⓕⓣ
  author_email: folktrash@gmail.com
  author_url: ''
  date: '2013-10-17 22:43:00 +0100'
  date_gmt: '2013-10-17 21:43:00 +0100'
  content: nice!
- id: 281
  author: Sm0ove
  author_email: harlekin87@gmail.com
  author_url: ''
  date: '2013-11-14 14:56:00 +0000'
  date_gmt: '2013-11-14 13:56:00 +0000'
  content: Your snippet fixed my issue within the blink of an eye! Thanks alot sir!
- id: 282
  author: John Babak
  author_email: babak.john@gmail.com
  author_url: ''
  date: '2013-11-15 07:06:00 +0000'
  date_gmt: '2013-11-15 06:06:00 +0000'
  content: window.location.port may return "80", not an empty string in some IE versions
    (window.location.host contains ":80" in this case, too). http://stackoverflow.com/questions/13167302/did-ie10-change-the-definition-of-window-location-port
- id: 286
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-11-20 20:36:00 +0000'
  date_gmt: '2013-11-20 19:36:00 +0000'
  content: Excellent spot John - I am going to post some updated code very soon.
- id: 362
  author: Frank Fang
  author_email: me@frankfang.com
  author_url: ''
  date: '2014-01-03 10:02:00 +0000'
  date_gmt: '2014-01-03 09:02:00 +0000'
  content: Nice hack. Thanks.
- id: 388
  author: Yuval Greenfield
  author_email: ubershmekel@gmail.com
  author_url: ''
  date: '2014-01-23 23:36:00 +0000'
  date_gmt: '2014-01-23 22:36:00 +0000'
  content: |-
    You might as well have a function for whenever you need to access location.origin

    https://gist.github.com/ubershmekel/8588187
- id: 389
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-23 23:39:00 +0000'
  date_gmt: '2014-01-23 22:39:00 +0000'
  content: |-
    Great idea!

    I guess the only issue with that is you need to remember to call this each time, with my code it just overrides the attribute if it doesn't already exist.
- id: 390
  author: Yuval Greenfield
  author_email: ubershmekel@gmail.com
  author_url: ''
  date: '2014-01-24 01:53:00 +0000'
  date_gmt: '2014-01-24 00:53:00 +0000'
  content: I guess I wanted it to be apparent in my code that a compatibility fix
    was used in case something was ever shuffled or used in a different context. E.g.
    on a site that doesn't have your fix pasted, or in code on your own site that
    runs before the fix is applied.
- id: 391
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-24 02:07:00 +0000'
  date_gmt: '2014-01-24 01:07:00 +0000'
  content: That makes sense!
- id: 423
  author: zlog
  author_email: contact@tutaktran.com
  author_url: ''
  date: '2014-03-07 00:18:00 +0000'
  date_gmt: '2014-03-06 23:18:00 +0000'
  content: Shouldn't "//" be "://"?
- id: 424
  author: zlog
  author_email: contact@tutaktran.com
  author_url: ''
  date: '2014-03-07 00:26:00 +0000'
  date_gmt: '2014-03-06 23:26:00 +0000'
  content: Actually, ignore me. `protocol` seems to include it.
- id: 436
  author: Gagan
  author_email: gagan.thakur.13@gmail.com
  author_url: ''
  date: '2014-03-28 09:07:00 +0000'
  date_gmt: '2014-03-28 08:07:00 +0000'
  content: "this \nwindow.location.hostname + (window.location.port ? ':' + window.location.port:
    '')\ncould be replaced by \nwindow.location.host ???"
- id: 437
  author: Juan Carlos Farah
  author_email: farah.juancarlos@gmail.com
  author_url: http://juancarlosfarah.com
  date: '2014-03-30 17:52:00 +0100'
  date_gmt: '2014-03-30 16:52:00 +0100'
  content: Yes. That's what I'm using. Is there a potential issue with window.location.host?
- id: 445
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-04-09 13:59:00 +0100'
  date_gmt: '2014-04-09 12:59:00 +0100'
  content: I am not sure if it is supported by older versions of IE, I would need
    to check but you could be right :-)
- id: 450
  author: BradBarbin
  author_email: brad@cmu.edu
  author_url: ''
  date: '2014-04-24 21:16:00 +0100'
  date_gmt: '2014-04-24 20:16:00 +0100'
  content: Thanks man
- id: 487
  author: chai
  author_email: kimchaily@hotmail.com
  author_url: ''
  date: '2014-05-22 11:03:00 +0100'
  date_gmt: '2014-05-22 10:03:00 +0100'
  content: wouldn't have thought of the port! great man, thx!
- id: 494
  author: crazy
  author_email: akdanaktl@gmail.com
  author_url: ''
  date: '2014-06-10 04:56:00 +0100'
  date_gmt: '2014-06-10 03:56:00 +0100'
  content: thank you! It helped me a lot!
- id: 500
  author: Gerardo Cruz
  author_email: gera4463@hotmail.com
  author_url: ''
  date: '2014-06-23 21:07:00 +0100'
  date_gmt: '2014-06-23 20:07:00 +0100'
  content: Nice yo save me a lot if time
- id: 540
  author: Mattia
  author_email: mattia.corciulo@gmail.com
  author_url: ''
  date: '2014-07-29 18:26:00 +0100'
  date_gmt: '2014-07-29 17:26:00 +0100'
  content: You make my day! tvtb
- id: 565
  author: Andre Z Sanchez
  author_email: aurumknight.ak@gmail.com
  author_url: ''
  date: '2014-08-29 20:29:00 +0100'
  date_gmt: '2014-08-29 19:29:00 +0100'
  content: |-
    For anyone using NPM, there's a nice little polyfill that implements this snippet here:
    https://github.com/shinnn/location-origin.js
- id: 566
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-08-29 22:04:00 +0100'
  date_gmt: '2014-08-29 21:04:00 +0100'
  content: Great share Andre!
- id: 624
  author: Andrew J
  author_email: jubas.andrzej@gmail.com
  author_url: ''
  date: '2014-10-09 13:32:00 +0100'
  date_gmt: '2014-10-09 12:32:00 +0100'
  content: This is exactly what I was looking for. Brilliant! Thanks for sharing.
- id: 629
  author: renish khunt
  author_email: renish.khunt@gmail.com
  author_url: ''
  date: '2014-10-28 08:50:00 +0000'
  date_gmt: '2014-10-28 07:50:00 +0000'
  content: Nice yo save me a lot if time. thank you so much.
- id: 634
  author: Sudarshan
  author_email: sudarshanhegde7@gmail.com
  author_url: ''
  date: '2014-11-07 10:27:00 +0000'
  date_gmt: '2014-11-07 09:27:00 +0000'
  content: Nyc.. Ty so much :-)
- id: 643
  author: Ashraf
  author_email: ashrafdop@gmail.com
  author_url: ''
  date: '2014-12-02 10:52:00 +0000'
  date_gmt: '2014-12-02 09:52:00 +0000'
  content: thanks for this post......
- id: 697
  author: Harsha
  author_email: harshapatil@hotmail.com
  author_url: ''
  date: '2015-02-24 14:29:00 +0000'
  date_gmt: '2015-02-24 13:29:00 +0000'
  content: works like a charm thank you :)
---
<p>Internet Explorer does not have access to <code>window.location.origin</code>, which is a bummer because it is a pretty handy variable to have, but we can make it work with a fairly straight forward check because we access <code>.origin</code>;</p>
<pre><code>if (!window.location.origin) {
  window.location.origin = window.location.protocol + "//" + window.location.hostname + (window.location.port ? ':' + window.location.port: '');
}</code></pre>
<p>This should now have <code>.origin</code> set to what you would expect.</p>
