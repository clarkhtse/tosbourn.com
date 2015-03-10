---
layout: post
status: publish
published: true
title: Some command line tips for the web developer
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1327
wordpress_url: http://tosbourn.com/?p=1327
date: '2013-02-21 17:48:12 +0000'
date_gmt: '2013-02-21 16:48:12 +0000'
categories:
- Other
tags:
- Command Line
- Linux
- Tips
comments: []
---
<p>I wanted to share some tips I have collated over the years that would be useful for web developers who occasionally need to roll their sleeves up and get their hands dirty working on a server. These are by no stretch of the imagination a complete list and nor do I get too specific. The tips below should work on the majority of Linux based web servers and should apply to the majority of setups.</p>
<h2>Where to get more help</h2>
<p>The first thing I should point out is that if at any time you get stuck or need help you should consult your sysadmin, if you have no sysadmin and need to consult the internet, I would suggest browsing and then asking on <a href="http://www.serverfault.com">ServerFault</a>, the people on that site seem to know their stuff and it is a vibrant enough community.</p>
<h2>Using Tab</h2>
<p>When typing file or folder names you can tab once to automatically complete the name, this can vastly speed up your time in the terminal, so instead of typing <code>vi /home/username/longFolderName/MyFileNameIsLongToo.txt</code> you could type <code>vi /h TAB u TAB l TAB M TAB</code>.</p>
<p>You can also double tap the tab key to see a list of options available, this is useful if you have two filenames and the tab autocomplete doesn't know what to do.</p>
<h2>Listing Files</h2>
<p>You probably already know the <code>ls</code> command, but did you know that by adding <code>-lah</code> after it you can greatly improve the detail you get back from it.</p>
<p><code>-l</code> lists everything out in a nicer format, <code>-a</code> includes hidden (dot) files in the list and <code>-h</code> makes thing like sizes human readable.</p>
<p>The other thing some people don't know about ls is that you can pass in the location you want to look at, so instead of typing <code>cd /home/user/</code> and then <code>ls</code> you can type <code>ls /home/user/</code></p>
<h2>Removing Files</h2>
<p>Again most people know about using <code>rm</code> to remove files, but some don't realise you can pass multiple files into it, for example <code>rm file1 file2</code></p>
<h2>Viewing Files</h2>
<p><code>cat</code> is your friend for quickly viewing the contents of a file, so you can just type <code>cat my_file.txt</code> instead of going into your text editor.</p>
<p>For larger files you might only want to see the very top of the file or the very bottom of the file, the quickest way to do that is to type <code>head my_file.txt</code> for the top or <code>tail my_file.txt</code> for the bottom of the file.</p>
<p>If you are constantly checking a debug file you can set up a quick command to constantly monitor it by typing <code>tail -f my_file.txt</code> this follows the file and it will automatically update as new stuff enters the file.</p>
<h2>Drive Space</h2>
<p>If you need to know how much space is on your drives just type <code>df -h</code>, you will normally get information for drives you probably didn't think existed, don't worry about it just focus on the ones that are clearly your main drives.</p>
<h2>RAM</h2>
<p>If you need to know how much RAM is installed on your machine just type <code>free -m</code>, the main column you will want to worry about is the 'total' one.</p>
<h2>History</h2>
<p>Did you just get shouted at because you forgot to prefix your command with sudo? Type <code>sudo !!</code> and it will run the last command as sudo.</p>
<p>If you know you entered a command a couple of commands ago, hit up a couple of times and the terminal will add it in for you.</p>
<p>If you used a command a while ago and want to be able to remember it, type <code>history</code> and you will see everything that you have typed in the last while come up along with a unique number for it. Take note of the number and type <code>![the number]</code> and the command will run.</p>
<h2>The Pipe Character</h2>
<p>The pipe character will take anything that would normally appear on the screen and passes it somewhere else, this is crazy handy for doing basic searches. So instead of typing history and scanning for every time you used sudo, type <code>history | grep sudo</code> and you will get only items with sudo in it.</p>
<h2>What is running</h2>
<p>Find out what is currently running by typing <code>top</code> — pay attention to the load average, if it is high there may be something going wrong. Generally look for a full disk, a process that is going mental or a load of traffic to the site.</p>
<p>If you just care about the load average you can get it on one line by typing <code>uptime</code>.</p>
<h2>Finding out More</h2>
<p><code>man</code> + any command will give you the manual for that command, super handy for finding out what you need without resorting to Google — also just like programs you run on your computer different versions could be installed on the server, this means that the man page will be more relevant sometimes than what google searches will tell you.</p>
<h2>Moving folder contents up a level quickly</h2>
<p>Move all contents of a folder into its parent with <code>mv child_dir/* ./</code></p>
<p>This means take everything in child_dir (but not directory called child_dir) and move it to the folder we are in. If you don't like the idea of typing <code>./</code> because it looks odd you can always type the full address.</p>
<h2>Alias Commands</h2>
<p>If there are long or complex commands that you type regularly you should alias them, this means creating another name you can reference the command by.</p>
<p>For example <code>alias lsa='ls -lah'</code> would allow you to type <code>lsa</code> and what would run would be <code>ls -lah</code>, you can even overwrite <code>ls</code> if you really wanted with <code>alias ls='ls -lah'</code>.</p>
<p>If you want to pass parameters you can create an alias with a function like this (just type it into the command line); <code>mkdir_ls() { mkdir $*; cd $*;}</code> then when you type <code>mkdir_ls new_folder</code> it will make a new folder and the move you into that folder.</p>
<h2>In closing</h2>
<p>Hopefully you find some of these useful, if you have any to add feel free to let me know on <a title="Some command line tips for the web developer" href="https://twitter.com/tosbourn">Twitter</a>.</p>
