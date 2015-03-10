---
layout: post
status: publish
published: true
title: Insert Gists without JavaScript
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1316
wordpress_url: http://tosbourn.com/?p=1316
date: '2013-02-14 00:11:32 +0000'
date_gmt: '2013-02-13 23:11:32 +0000'
categories:
- Development Help
tags:
- JavaScript
- Github
- Gists
comments:
- id: 413
  author: Nikita Avvakumov
  author_email: nikitaavvakumov@gmail.com
  author_url: ''
  date: '2014-02-23 19:02:00 +0000'
  date_gmt: '2014-02-23 18:02:00 +0000'
  content: Toby, thanks for this tip! My only modification to your method is to leave
    the double spaces in the gist file intact as this gives proper code indentation.
    Cheers.
- id: 528
  author: Steven Buehler
  author_email: stevenbuehlerfl@gmail.com
  author_url: http://www.swbuehler.com
  date: '2014-07-20 04:23:00 +0100'
  date_gmt: '2014-07-20 03:23:00 +0100'
  content: This is an awesome tip to use in my blog that's driven by SharePoint, which
    doesn't allow the use of scripts. The only change I had to make was to remove
    the line numbering because in SharePoint blogs it doesn't line up correctly (I
    remove everything from  to the  at the end of that cell to get rid of the line
    numbers.
- id: 529
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-07-20 11:33:00 +0100'
  date_gmt: '2014-07-20 10:33:00 +0100'
  content: Thanks for sharing this Steven - I haven't used sharepoint before but this
    will be invaluable to folk who do!
- id: 530
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-07-20 11:34:00 +0100'
  date_gmt: '2014-07-20 10:34:00 +0100'
  content: I can't believe I didn't spot the indentation problems before, thanks so
    much Nikita!
---
<p>If you would like to insert Github's Gists into your blog posts or pages but don't want the overhead or potential security implications of loading some JavaScript from a third party then it is relatively straight forward to get around.</p>
<p>Here is a gist I have created just for this post - <a href="https://gist.github.com/tosbourn/4949176">https://gist.github.com/tosbourn/4949176</a></p>
<p>And here is the JavaScript file I am meant to include;</p>
<p>&lt;script src="https://gist.github.com/tosbourn/4949176.js"&gt;&lt;/script&gt;</p>
<p>But instead of including it, lets visit the JavaScript file at <a href="https://gist.github.com/tosbourn/4949176.js">https://gist.github.com/tosbourn/4949176.js</a></p>
<p>Well, well, well! Looks like it is just some Document.Writes, those guys are pretty easy to work with, so lets copy the entire thing and paste it into a text editor.</p>
<p>Once in the text editor we need to run a find and replace on a three things;</p>
<ol>
<li>Find any reference of \n and remove it.</li>
<li>Find any reference of \ and remove it.</li>
<li>Find any double spaces and remove them.</li>
</ol>
<p>Then just remove the <code>document.write('</code> and <code>');</code> from the start and end of the two lines.</p>
<p>You are left with something like this;</p>
<pre><code>&lt;link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" media="screen" rel="stylesheet" /&gt;
&lt;div id="gist4949176"&gt;&lt;div&gt;&lt;div&gt;&lt;div&gt;&lt;table cellpadding="0" cellspacing="0"&gt;&lt;tr&gt;&lt;td&gt;&lt;span id="file-gistfile1-txt-L1" rel="file-gistfile1-txt-L1"&gt;1&lt;/span&gt;&lt;span id="file-gistfile1-txt-L2" rel="file-gistfile1-txt-L2"&gt;2&lt;/span&gt;&lt;span id="file-gistfile1-txt-L3" rel="file-gistfile1-txt-L3"&gt;3&lt;/span&gt;&lt;/td&gt;&lt;td&gt;&lt;pre&gt;&lt;div id="file-gistfile1-txt-LC1"&gt;Here is my Gist!&lt;/div&gt;&lt;div id="file-gistfile1-txt-LC2"&gt;Look at it!&lt;/div&gt;&lt;div id="file-gistfile1-txt-LC3"&gt;Gisting all over the place&lt;/div&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;&lt;/div&gt;&lt;/div&gt;&lt;div&gt;&lt;a href="https://gist.github.com/tosbourn/4949176/raw/678465ea9db744f03fa7628745942fae281d1123/gistfile1.txt" style="float:right"&gt;view raw&lt;/a&gt;&lt;a href="https://gist.github.com/tosbourn/4949176#file-gistfile1-txt" style="float:right; margin-right:10px; color:#666;"&gt;gistfile1.txt&lt;/a&gt;&lt;a href="https://gist.github.com/tosbourn/4949176"&gt;This Gist&lt;/a&gt; brought to you by &lt;a href="http://github.com"&gt;GitHub&lt;/a&gt;.&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;		
</code></pre>
<p>Now we are almost there, we could include this on our page and no JavaScript would run, but we do still need to go across to Github to grab the CSS file and of course there will be a slight performance hit with that, so lets go on over to <code>https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css</code> and grab the CSS.</p>
<p>Now we simply replace the first line of our code from the <code>link</code> element to a <code>style</code> block and include the CSS, now all that is left is to copy and paste this code from our text editor into our website.</p>
<p>Here is the result sans external calls;</p>
<style type="text/css"><!--<br />
.gist{color:#000}.gist .gist-file{border:1px solid #dedede;font-family:Consolas, "Liberation Mono", Courier, monospace;margin-bottom:1em}.gist .gist-file .gist-meta{font-family:Helvetica, arial, freesans, clean, sans-serif;overflow:hidden;font-size:85%;padding:.5em;color:#666;background-color:#eaeaea}.gist .gist-file .gist-meta a{color:#369}.gist .gist-file .gist-meta a:visited{color:#737}.gist .gist-file .gist-data{overflow:auto;word-wrap:normal;background-color:#f8f8ff;border-bottom:1px solid #ddd;font-size:100%}.gist .gist-file .gist-data .line-data{padding:.5em !important}.gist .gist-file .gist-data .line-pre{font-family:Consolas, "Liberation Mono", Courier, monospace;background:transparent !important;border:none !important;margin:0 !important;padding:0 !important}.gist .gist-file .gist-data .gist-highlight{background:transparent !important}.gist .gist-file .gist-data .line-numbers{background-color:#ececec;color:#aaa;border-right:1px solid #ddd;text-align:right;padding:.5em}.gist .gist-file .gist-data .line-numbers .line-number{clear:right;display:block}.gist-syntax{background:#ffffff}.gist-syntax .c{color:#999988;font-style:italic}.gist-syntax .err{color:#a61717;background-color:#e3d2d2}.gist-syntax .k{color:#000000;font-weight:bold}.gist-syntax .o{color:#000000;font-weight:bold}.gist-syntax .cm{color:#999988;font-style:italic}.gist-syntax .cp{color:#999999;font-weight:bold}.gist-syntax .c1{color:#999988;font-style:italic}.gist-syntax .cs{color:#999999;font-weight:bold;font-style:italic}.gist-syntax .gd{color:#000000;background-color:#ffdddd}.gist-syntax .gd .x{color:#000000;background-color:#ffaaaa}.gist-syntax .ge{color:#000000;font-style:italic}.gist-syntax .gr{color:#aa0000}.gist-syntax .gh{color:#999999}.gist-syntax .gi{color:#000000;background-color:#ddffdd}.gist-syntax .gi .x{color:#000000;background-color:#aaffaa}.gist-syntax .go{color:#888888}.gist-syntax .gp{color:#555555}.gist-syntax .gs{font-weight:bold}.gist-syntax .gu{color:#aaaaaa}.gist-syntax .gt{color:#aa0000}.gist-syntax .kc{color:#000000;font-weight:bold}.gist-syntax .kd{color:#000000;font-weight:bold}.gist-syntax .kp{color:#000000;font-weight:bold}.gist-syntax .kr{color:#000000;font-weight:bold}.gist-syntax .kt{color:#445588;font-weight:bold}.gist-syntax .m{color:#009999}.gist-syntax .s{color:#d14}.gist-syntax .na{color:#008080}.gist-syntax .nb{color:#0086B3}.gist-syntax .nc{color:#445588;font-weight:bold}.gist-syntax .no{color:#008080}.gist-syntax .ni{color:#800080}.gist-syntax .ne{color:#990000;font-weight:bold}.gist-syntax .nf{color:#990000;font-weight:bold}.gist-syntax .nn{color:#555555}.gist-syntax .nt{color:#000080}.gist-syntax .nv{color:#008080}.gist-syntax .ow{color:#000000;font-weight:bold}.gist-syntax .w{color:#bbbbbb}.gist-syntax .mf{color:#009999}.gist-syntax .mh{color:#009999}.gist-syntax .mi{color:#009999}.gist-syntax .mo{color:#009999}.gist-syntax .sb{color:#d14}.gist-syntax .sc{color:#d14}.gist-syntax .sd{color:#d14}.gist-syntax .s2{color:#d14}.gist-syntax .se{color:#d14}.gist-syntax .sh{color:#d14}.gist-syntax .si{color:#d14}.gist-syntax .sx{color:#d14}.gist-syntax .sr{color:#009926}.gist-syntax .s1{color:#d14}.gist-syntax .ss{color:#990073}.gist-syntax .bp{color:#999999}.gist-syntax .vc{color:#008080}.gist-syntax .vg{color:#008080}.gist-syntax .vi{color:#008080}.gist-syntax .il{color:#009999}<br />
--></style>
<div class="gist" id="gist4949176">
<div class="gist-file">
<div class="gist-data gist-syntax">
<div class="file-data">
<table class="lines highlight" cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td class="line-numbers"><span class="line-number" id="file-gistfile1-txt-L1">1</span><span class="line-number" id="file-gistfile1-txt-L2">2</span><span class="line-number" id="file-gistfile1-txt-L3">3</span></td>
<td class="line-data">
<div class="line" id="file-gistfile1-txt-LC1">Here is my Gist!</div>
<div class="line" id="file-gistfile1-txt-LC2">Look at it!</div>
<div class="line" id="file-gistfile1-txt-LC3">Gisting all over the place</div>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<div class="gist-meta"><a style="float: right;" href="https://gist.github.com/tosbourn/4949176/raw/678465ea9db744f03fa7628745942fae281d1123/gistfile1.txt">view raw</a><a style="float: right; margin-right: 10px; color: #666;" href="https://gist.github.com/tosbourn/4949176#file-gistfile1-txt">gistfile1.txt</a><a href="https://gist.github.com/tosbourn/4949176">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.</div>
</div>
</div>
<p>I think it works well and you can't deny the performance benefits.</p>
<p>You can also make this process a bit smoother by requesting the .json or .txt versions of the Gist, in our example change .js to either .json or .txt, like so: <a href="https://gist.github.com/tosbourn/4949176.txt">https://gist.github.com/tosbourn/4949176.txt</a></p>
<p>Thanks so much to <a href="https://twitter.com/PunKeel">PunKeel</a> for suggesting the .json or .txt variants.</p>
