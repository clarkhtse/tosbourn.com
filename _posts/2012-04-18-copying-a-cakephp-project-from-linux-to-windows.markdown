---
layout: post
status: publish
published: true
title: Copying a CakePHP Project from Linux to Windows
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 986
wordpress_url: http://tosbourn.com/?p=986
date: '2012-04-18 11:11:35 +0100'
date_gmt: '2012-04-18 10:11:35 +0100'
categories:
- Development Help
tags:
- PHP
- Linux
- Windows 7
- CakePHP
comments:
- id: 141
  author: Test
  author_email: test@gmail.com
  author_url: ''
  date: '2012-05-23 11:08:00 +0100'
  date_gmt: '2012-05-23 10:08:00 +0100'
  content: |-
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
    test 
- id: 142
  author: Test
  author_email: test@ddd.aaa
  author_url: ''
  date: '2012-05-23 11:08:00 +0100'
  date_gmt: '2012-05-23 10:08:00 +0100'
  content: mast
---
<p>Recently I had to make some changes to a website built on top of the CakePHP framework.</p>
<p>Most of the time I would develop within a Linux environment, making the edits locally and running them on a development server before pushing them onto a production server - the development server being pretty much a clone of the production server.</p>
<p>This time however I opted to do the changes locally (there were a lot of small changes that make pushing to a development server a bit of a pain).</p>
<p>My setup is Windows 7 with XAMPP installed on it, but the stages I had to follow should be similar for most setups.</p>
<p>I already had the website code downloaded onto my machine as that is where I make the edits - once I set up my hosts file in Windows and the virtual host directives in Apache I figured I would be 90% of the way there. I wish!</p>
<p>The first issue I encountered was this:</p>
<pre>Warning: include(cake\bootstrap.php) [function.include]: failed to open stream: No such file or directory in C:\path\to\my\site\webroot\index.php on line 78

Warning: include() [function.include]: Failed opening 'cake\bootstrap.php' for inclusion (include_path='/path/to/cake') in C:\path\to\my\site\webroot\index.php on line 78

Fatal error: CakePHP core could not be found. Check the value of CAKE_CORE_INCLUDE_PATH in APP/webroot/index.php. It should point to the directory containing your \cake core directory and your \vendors root directory. in C:\path\to\my\site\webroot\index.php on line 79</pre>
<p>Obviously you go where the errors take you, sure enough if I open webroot/index.php I can see that it is linking to a folder structure that I don't have locally.</p>
<p>I jump onto the development machine and grab the files that it was linking to, pull them into a folder and put the correct path in, like so:</p>
<pre>if (!defined('CAKE_CORE_INCLUDE_PATH')) {
		//define('CAKE_CORE_INCLUDE_PATH', "/old/linux/path/cake" );
		define('CAKE_CORE_INCLUDE_PATH', "C:\new\windows\path\cake" );
	}</pre>
<p>Now when I go to my site I get this error:</p>
<pre>An Internal Error Has Occurred</pre>
<p>Useful! But before that displays I do get some of my layout displaying on screen, so there is a bit of progress.</p>
<p>In order to squeeze some more information out of cake I go into config/core.php and change the debug level.</p>
<pre>//Configure::write('debug', 0);
Configure::write('debug', 2);</pre>
<p>Now when I refresh the page I get plenty of useful information! In my case it was because I was an idiot and forgot to hook up my database - I won't go through the steps to do that but basically export the development database, import it into your local and make sure you set up the same users with the same privileges.</p>
<p>I tend to try and keep my local setup the same as development so I am not messing about with config files too much.</p>
<p>My next issue that is immediately apparent after a refresh is that CSS is not getting loaded (and I am going to guess that JavaScript isn't getting loaded either).</p>
<p>I have found that the best way to begin to track down this sort of issue is to view the source of the page, first of all is the code in place to try and load in CSS? In my case it was.</p>
<p>Next question, does the path to the CSS file look right? Again in my case it does.</p>
<p>Final question, when you click on the link to the CSS file, does it load? In my case it does not.</p>
<p>This immediately feels like an issue with either Apache or .htaccess redirects.</p>
<p>First let me check Apache to make sure that mod_rewrite is turned on, I check my httpd.conf file and sure enough it is enabled. Which means there is probably something wrong with how my site is locally trying to rewrite things. Onto .htaccess!</p>
<p>Annoyingly in my case htaccess was fine - in my case it turns out that I stupidly didn't have my path in my virtual host set to the webroot, once I added this into my virtual host directive and restarted Apache I started to get my CSS again.</p>
<p>That is almost us finished - everything seems to be working but there was one edit made earlier that needs to be tidied up - the location of the Cake folder is something you want to worry about long term, having to remember to change that whenever you move code about is just a pain.</p>
<p>You don't want to exclude webroot/index.php from any deployment solution because at some stage you might change something that you want to deploy, so I suggest doing something like this:</p>
<pre>	if (!defined('CAKE_CORE_INCLUDE_PATH')) {
	    $currenturi = $_SERVER['DOCUMENT_ROOT'];
	    $mypos = strpos($currenturi, 'C:');
	    if ($mypos !== false) {
	    	define('CAKE_CORE_INCLUDE_PATH', "C:\my\windows\path\to\cake" );
	    } else {
	    	define('CAKE_CORE_INCLUDE_PATH', "/linux/path/to/cake" );
	    }		
	}</pre>
<p>This will check for "C:" in the document_root variable, if it is there then we must be on a Windows machine, so lets display our local path. If not the Linux path will be used. (Note, it isn't just because this is Windows vs Linux, any two setups can do this - with Linux to Linux you might have your files in your home directory, in which case you would look up your name as the differentiator)</p>
