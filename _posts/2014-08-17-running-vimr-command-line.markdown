---
layout: post
status: publish
published: true
title: Running VimR From the Command Line
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2298
wordpress_url: http://tosbourn.com/?p=2298
date: '2014-08-17 01:03:13 +0100'
date_gmt: '2014-08-17 00:03:13 +0100'
categories:
- Other
tags:
- VimR
comments: []
---
<p>If you want to open <a title="VimR – A first look" href="http://tosbourn.com/vimr-first-look/">VimR</a> from the command line here is what you need to do;</p>
<p>Create a bash script in <code>/usr/local/bin/</code> called <code>vimr</code></p>
<p>In that file write the following;</p>
<pre><code>#!/bin/bash

open -a VimR.app "$@"
</code></pre>
<p>Make the script writeable by calling <code>chmod u+x vimr</code>.</p>
<p>Now you can call vimr filename to open a specific file or folder, or if you call <code>vimr .</code> it will open the current working directory in VimR.</p>
<h2>Notes</h2>
<ul>
<li>Thanks so much <a href="https://github.com/dnerdy">dnerdy</a> for posting this script in a <a href="https://github.com/qvacua/vimr/issues/99#issuecomment-52409208">GitHub Issue</a> I created.</li>
<li>You don't need to have this in /usr/local/bin/ it can be anywhere that can be seen in your path.</li>
</ul>
