---
layout: post
status: publish
published: true
title: Open all your browsers at once in OSx
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1360
wordpress_url: http://tosbourn.com/?p=1360
date: '2013-03-18 15:53:39 +0000'
date_gmt: '2013-03-18 14:53:39 +0000'
categories:
- Development Help
tags:
- Firefox
- Testing
- Browsers
- Google Chrome
- Paul Irish
- Firefox Nightly
- Google Chrome Canary
- Opera
- Opera Next
comments: []
---
<p>So here is the problem, you have one browser that you want to spend most of your day in, this will be Firefox or if you are a lesser being Chrome or Opera or something, but when you want to test your web-thing in various browsers you need to go and manually open them up.</p>
<p>Manually doing stuff is boring so I wrote a quick function to open up all the browsers at once from another application that I spend all day in, the Terminal.</p>
<p>Without further ado here is the code;</p>
<pre><code>function browser() {
    /Applications/Firefox.app/Contents/MacOS/firefox $1 &lt; /dev/null &gt;&amp;/dev/null &amp;
    /Applications/FirefoxNightly.app/Contents/MacOS/firefox -no-remote -P nightly $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
    /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome  $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
    /Applications/Google\ Chrome\ Canary.app/Contents/MacOS/Google\ Chrome\ Canary $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
    /Applications/Opera.app/Contents/MacOS/Opera $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
    /Applications/Opera\ Next.app/Contents/MacOS/Opera $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
    /Applications/Safari.app/Contents/MacOS/Safari $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
    /Applications/Webkit.app/Contents/MacOS/Webkit $1 &lt;/dev/null &amp;&gt;/dev/null &amp;
}</code></pre>
<p>Here are a few notes about the code;</p>
<ul>
<li>This is geared up for my system, if you have called your browsers something different you will need to edit them.</li>
<li>This is opening up the following browsers - Firefox, Firefox Nightly, Google Chrome, Google Chrome Canary, Opera, Opera Next, Safari and Webkit Nightly</li>
<li>I had to do some external setup to get Firefox and Firefox Nightly working together (more on that in a second)</li>
<li>If you pass in a URL when calling browser it will open the browsers with that URL</li>
</ul>
<p>Basically all this is doing is creating a function you can call from the command line called browser, this function will run each line in turn. All each line does is open the binary stored within your .app folder.</p>
<p>The <code>&lt;/dev/null &amp;&gt;/dev/null &amp;</code> part of the line simply says to the terminal, don't bother me with any output from these browsers, it effectively detaches them from the terminal.</p>
<p>To 'install' this script you should edit your .bash_profile, you can do this by calling <code>vi ~/.bash_profile</code> and copying the above script into it.</p>
<p>Once you have copied it in you will need to force your terminal to read the update file, you do this by running <code>source ~/.bash_profile</code></p>
<p>Now you can call the script whenever you want from your terminal by typing <code>browser www.mysite.com<br />
</code></p>
<h2>Firefox</h2>
<p>OK so you aren't meant to have two Firefox profiles running at once so what I had to do is run Firefox Nightly using a separate profile, this is pretty easy to setup.</p>
<p>First you need to create a new profile, you can do that by running the following command;</p>
<p><code>/Applications/Firefox.app/Contents/MacOS/firefox -CreateProfile nightly</code></p>
<p>This will create a new profile called nightly, then you can associate that profile with Firefox Nightly as I have done above.</p>
<h2>Alfred</h2>
<p>If you are an Alfred poweruser you can download <a href="http://tosbourn.com/s/browser.alfredextension">this script</a> that will call browser for you if you aren't already in the terminal.</p>
<h2>Resources</h2>
<p>I had to use some other articles during research for this bit of code and I couldn't have written it without them!</p>
<ul>
<li><a href="http://kb.mozillazine.org/Command_line_arguments">Firefox Command Line Arguments</a></li>
<li><a href="http://superuser.com/a/178592/19493">How to detach a process</a></li>
</ul>
<p>If you need to download any of the browsers mentioned, here you go!</p>
<ul>
<li><a href="http://www.mozilla.org/en-US/firefox/new/">Firefox</a></li>
<li><a href="http://nightly.mozilla.org/">Firefox Nightly</a></li>
<li><a href="https://www.google.com/intl/en/chrome/browser/">Google Chrome</a></li>
<li><a href="https://www.google.co.uk/intl/en/chrome/browser/canary.html">Google Chrome Canary</a></li>
<li><a href="http://www.opera.com/computer/mac">Opera</a></li>
<li><a href="http://snapshot.opera.com/mac/latest">Opera Next</a></li>
<li><a href="http://www.apple.com/safari/">Safari</a></li>
<li><a href="http://nightly.webkit.org/">Webkit</a></li>
</ul>
<p>And last but not least, this was inspired by a talk <a href="http://paulirish.com/">Paul Irish</a> gave, you can view it here.</p>
<p><iframe src="http://www.youtube.com/embed/vDbbz-BdyYc" height="315" width="560" allowfullscreen="" frameborder="0"></iframe></p>
