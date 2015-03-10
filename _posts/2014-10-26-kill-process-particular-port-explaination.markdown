---
layout: post
status: publish
published: true
title: Kill off any process on a particular port - An explaination
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2358
wordpress_url: http://tosbourn.com/?p=2358
date: '2014-10-26 21:50:22 +0000'
date_gmt: '2014-10-26 20:50:22 +0000'
categories:
- Development Help
tags:
- Process
- Unix
- Kill
comments: []
---
<p>For what feels like forever I have had to manually search for and then copy and paste code something like;</p>
<pre><code>lsof -wni tcp:5000 | awk 'NR&gt;1{kill -9 $2}'</code></pre>
<p>So much so that recently I created a <a href="https://gist.github.com/tosbourn/35092eb714203eaa75e6">gist</a> so at least I had some control of it and had a central place I could search.</p>
<p>I wanted to explain the three main parts to this, partly to help out folk who are lost and partly because I am not too sure myself what all the flags are doing.</p>
<p>First, let me break this down into pseudocode;</p>
<ol>
<li>Get a list of all processes using port 5000</li>
<li>Tidy up the list we receive to give us just the ID of the processes</li>
<li>Kill the processes</li>
</ol>
<p>These seem like sensible things to do, so let me talk about each one of them in detail.</p>
<h2>Get a list of all processes using a port number</h2>
<p>The first part of our one liner is actually the most alien to me. Lets start by finding out what the heck lsof stands for, then we will worry about the flags and the input.</p>
<pre><code>man lsof</code></pre>
<p>Running the man command brings up the manual for a given program, in our case lsof. Immediately we have learned something, it stands of list open files (ls being the command to list files in Unix like operating systems).</p>
<p>At first I thought this seemed very odd, I mean we want to kill stuff on a port, is a port a file? Reading the description gives us (bolding mine);</p>
<blockquote><p>An open file may be a regular file, a directory, a block special file, a character special file, an executing text reference, a library, a stream or <strong>a net-</strong><br />
<strong> work file (Internet socket, NFS file or UNIX domain socket.)</strong> A specific file or all the files in a file system may be selected by path.</p></blockquote>
<p>Cool, so that makes a little more sense, but what about the -wni flags we pass into it?</p>
<p>Again man helps us there, reading through the documentation you can find out all about the flags you can use.</p>
<ul>
<li>w — Disables warning messages.</li>
<li>n — Inhibits  the  conversion  of network numbers to host names for network files.</li>
<li>i — selects the listing of files any of whose Internet address matches the address specified in i. As is in our case, if no address is specified, this option selects the listing of all Internet and x.25 (HP-UX) network files.</li>
</ul>
<p>Finally, after these flags we pass in our actual input, tcp:5000 - all this is doing is say look for open files on the tcp port 5000.</p>
<p>So what happens when we actually run this command when we have something running on port 5000, I am going to spin up a rails server on that port and run the command;</p>
<pre>COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME
ruby 80077 tobyosbourn 11u IPv4 0xadc692f51faed72f 0t0 TCP *:commplex-main (LISTEN)</pre>
<p>For our purposes the output gives us the Process ID, which is what we want, but for the sake of completeness lets talk about everything here;</p>
<ul>
<li>COMMAND — The command using port 5000, in our case, ruby</li>
<li>PID — The Process ID</li>
<li>USER — The User who ran the command</li>
<li>FD — The File Descriptor Number for the file. In our case 11u, the 'u' part means there is read and write access on the file.</li>
<li>TYPE — The type of node associated with the file, since it is a networking file ours is IPv4</li>
<li>DEVICE — This can mean many things, but since we are dealing with a socket this is the base address of the device.</li>
<li>SIZE/OFF — This is either the size of the file or the size of the file offset in bytes</li>
<li>NODE — In our case this is the internet protocol being used (TCP)</li>
<li>NAME — Again this can have many meanings depending on the type of file, for us this is the nice name of port 5000 (something I didn't know!)</li>
</ul>
<h2>Tidy up the output from lsof</h2>
<p>As you can see there is a lot of pretty useful output we get when running such a simple command, but for our purposes we only care about the PID, this is where <code>awk</code> comes in.</p>
<p><code>awk</code> is a program for pattern scanning and processing text, it is crazy powerful and the learning curve isn't as steep as you might imagine.</p>
<p>Lets start by simplifying our command, so instead of;</p>
<pre><code>awk 'NR&gt;1{kill -9 $2}'</code></pre>
<p>We have;</p>
<pre><code>awk 'NR&gt;1{print $2}'</code></pre>
<p>That might still look as clear as mud to you, but let me explain from left to right;</p>
<p>NR&gt;1 says, ignore any line number less than 1, we count from 0 so what this means is, don't worry about the titles in our output.</p>
<p>{} says do the command inside me once per line</p>
<p><code>print $2</code> is a bash command, this is saying print whatever is stored in $2. The magic part is that awk has seen that the output has a clear boundary between words so will only print the second word it sees, which in our case is the PID.</p>
<p>Running this print command means the output that was;</p>
<pre>COMMAND PID USER FD TYPE DEVICE SIZE/OFF NODE NAME
ruby 80077 tobyosbourn 11u IPv4 0xadc692f51faed72f 0t0 TCP *:commplex-main (LISTEN)</pre>
<p>Becomes;</p>
<pre><code>80077</code></pre>
<p>Excellent! This is exactly what we want!</p>
<h2>Kill the processes</h2>
<p>Well, it is *almost* what we want, in our last set of examples we changed our code to print the PID we want. Lets be honest, we don't actually care what the PID is, we just want the process to be killed!</p>
<p>That is when <code>kill -9</code> comes in.</p>
<p>The flag 9 references the signal that we will send to the process and we pass in the process ID within that process group we want to kill.</p>
<p>The signals you can send are;</p>
<ul>
<li>1 — HUP (hang up)</li>
<li>2 — <span style="line-height: 1.5;">INT (interrupt)</span></li>
<li>3 — <span style="line-height: 1.5;">QUIT (quit)</span></li>
<li>6 — <span style="line-height: 1.5;">ABRT (abort)</span></li>
<li>9 — <span style="line-height: 1.5;">KILL (non-catchable, non-ignorable kill)</span></li>
<li>14 — <span style="line-height: 1.5;">ALRM (alarm clock)</span></li>
<li>15 — <span style="line-height: 1.5;">TERM (software termination signal)</span></li>
</ul>
<p>I hope this has helped clear up what is actually happening when you run that command!</p>
