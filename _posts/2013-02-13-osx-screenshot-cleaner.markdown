---
layout: post
status: publish
published: true
title: OSx Screenshot Cleaner
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1311
wordpress_url: http://tosbourn.com/?p=1311
date: '2013-02-13 23:51:18 +0000'
date_gmt: '2013-02-13 22:51:18 +0000'
categories:
- Other
tags:
- OSx
- Ruby
comments: []
---
<p>If, like me, you are prone to taking one too many screenshots using <code>cmd+shift+3</code> and <code>cmd+shift+4</code> then you are probably used to your desktop being littered with screenshot image files.</p>
<p>Normally they mount up on me something fierce because I take the screenshot then do something with it immediately but never go back to delete/move/rename the file.</p>
<p>Don't worry though, help is at hand! I have created a very small Ruby script that you can tie in with a crontab to move screenshots into a screenshot folder on a regular basis!</p>
<p>Please check out the <a href="https://github.com/tosbourn/osx-screenshot-cleaner">OSx Screenshot Cleaner on Github</a>.</p>
<p>This could have been done in pretty much any language, but I am going through a Ruby phase right now, here was the first version of my code (I say first because this could change based on feedback);</p>
<link href="https://gist.github.com/assets/embed-0af287a4b5c981db301049e56f06e5d3.css" rel="stylesheet" media="screen" />
<div class="gist" id="gist4949062">
<div class="gist-file">
<div class="gist-data gist-syntax">
<div class="file-data">
<table class="lines highlight" cellspacing="0" cellpadding="0">
<tbody>
<tr>
<td class="line-numbers"><span class="line-number" id="file-gistfile1-rb-L1">1</span> <span class="line-number" id="file-gistfile1-rb-L2">2</span> <span class="line-number" id="file-gistfile1-rb-L3">3</span> <span class="line-number" id="file-gistfile1-rb-L4">4</span> <span class="line-number" id="file-gistfile1-rb-L5">5</span> <span class="line-number" id="file-gistfile1-rb-L6">6</span> <span class="line-number" id="file-gistfile1-rb-L7">7</span> <span class="line-number" id="file-gistfile1-rb-L8">8</span> <span class="line-number" id="file-gistfile1-rb-L9">9</span> <span class="line-number" id="file-gistfile1-rb-L10">10</span> <span class="line-number" id="file-gistfile1-rb-L11">11</span> <span class="line-number" id="file-gistfile1-rb-L12">12</span> <span class="line-number" id="file-gistfile1-rb-L13">13</span> <span class="line-number" id="file-gistfile1-rb-L14">14</span> <span class="line-number" id="file-gistfile1-rb-L15">15</span> <span class="line-number" id="file-gistfile1-rb-L16">16</span> <span class="line-number" id="file-gistfile1-rb-L17">17</span> <span class="line-number" id="file-gistfile1-rb-L18">18</span></td>
<td class="line-data">
<div class="line" id="file-gistfile1-rb-LC1"><span class="nb">require</span> <span class="s1">'FileUtils'</span></div>
<div class="line" id="file-gistfile1-rb-LC2"></div>
<div class="line" id="file-gistfile1-rb-LC3"><span class="n">homepath</span> <span class="o">=</span> <span class="no">File</span><span class="o">.</span><span class="n">expand_path</span> <span class="s2">"~"</span></div>
<div class="line" id="file-gistfile1-rb-LC4"><span class="n">desktop_files</span> <span class="o">=</span> <span class="no">Dir</span><span class="o">.</span><span class="n">entries</span> <span class="n">homepath</span> <span class="o">+</span> <span class="s2">"/Desktop"</span></div>
<div class="line" id="file-gistfile1-rb-LC5"><span class="n">desktop_files</span><span class="o">.</span><span class="n">to_a</span></div>
<div class="line" id="file-gistfile1-rb-LC6"><span class="n">screen_shot_folder</span> <span class="o">=</span> <span class="n">homepath</span> <span class="o">+</span> <span class="s2">"/Desktop/Screenshots"</span></div>
<div class="line" id="file-gistfile1-rb-LC7"></div>
<div class="line" id="file-gistfile1-rb-LC8"><span class="ss">Dir</span><span class="p">:</span><span class="ss">:mkdir</span><span class="p">(</span><span class="n">screen_shot_folder</span><span class="p">)</span> <span class="k">unless</span> <span class="no">File</span><span class="o">.</span><span class="n">exists?</span><span class="p">(</span><span class="n">screen_shot_folder</span><span class="p">)</span></div>
<div class="line" id="file-gistfile1-rb-LC9"></div>
<div class="line" id="file-gistfile1-rb-LC10"><span class="n">desktop_files</span><span class="o">.</span><span class="n">each</span> <span class="p">{</span></div>
<div class="line" id="file-gistfile1-rb-LC11"><span class="o">    |</span><span class="n">the_file</span><span class="o">|</span></div>
<div class="line" id="file-gistfile1-rb-LC12"><span class="k">    if</span> <span class="n">the_file</span><span class="o">.</span><span class="n">include?</span> <span class="s2">"Screen Shot"</span></div>
<div class="line" id="file-gistfile1-rb-LC13"><span class="n">        old_file</span> <span class="o">=</span> <span class="n">homepath</span> <span class="o">+</span> <span class="s2">"/Desktop/"</span> <span class="o">+</span> <span class="n">the_file</span></div>
<div class="line" id="file-gistfile1-rb-LC14"><span class="n">        new_file</span> <span class="o">=</span> <span class="n">screen_shot_folder</span> <span class="o">+</span> <span class="s2">"/"</span> <span class="o">+</span> <span class="n">the_file</span></div>
<div class="line" id="file-gistfile1-rb-LC15"></div>
<div class="line" id="file-gistfile1-rb-LC16"><span class="no">        FileUtils</span><span class="o">.</span><span class="n">mv</span><span class="p">(</span><span class="n">old_file</span><span class="p">,</span><span class="n">new_file</span><span class="p">,</span> <span class="ss">:force</span> <span class="o">=&gt;</span> <span class="kp">true</span><span class="p">)</span></div>
<div class="line" id="file-gistfile1-rb-LC17"><span class="k">    end</span></div>
<div class="line" id="file-gistfile1-rb-LC18"><span class="p">}</span></div>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<div class="gist-meta"><a style="float: right;" href="https://gist.github.com/tosbourn/4949062/raw/e83cd504ff210c9a28a7a20463b1d874f22a269c/gistfile1.rb">view raw</a> <a style="float: right; margin-right: 10px; color: #666;" href="https://gist.github.com/tosbourn/4949062#file-gistfile1-rb">gistfile1.rb</a> <a href="https://gist.github.com/tosbourn/4949062">This Gist</a> brought to you by <a href="http://github.com">GitHub</a>.</div>
</div>
</div>
<p><strong>Line 1</strong>:  We include the FileUtils package because we will be using parts of it later.<br />
<strong>Line 2</strong>: I find the home directory, expand it out and save it to a variable.<br />
<strong>Line 3</strong>: I grab all the files held within the Desktop folder of the home directory.<br />
<strong>Line 4</strong>: I convert all these files to an array so that I can later loop through them.<br />
<strong>Line 5</strong>: I create a string that shows where I want my screenshots to be placed later.<br />
<strong>Line 6</strong>: If the screenshot folder doesn't exist create it.<br />
<strong>Line 7</strong>: Loop through each of the desktop files.<br />
<strong>Line 9</strong>: Check to make sure they include the term "Screen Shot"<br />
<strong>Line 10</strong>: Create a string to represent the old file.<br />
<strong>Line 11</strong>: Create a string to represent the new file.<br />
<strong>Line 12</strong>: Move the old file to the new file.</p>
