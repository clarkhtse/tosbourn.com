---
layout: post
status: publish
published: true
title: Having FTP in your IDE is part of a broken model
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 801
wordpress_url: http://tosbourn.com/?p=801
date: '2012-01-12 23:29:44 +0000'
date_gmt: '2012-01-12 22:29:44 +0000'
categories:
- Other
tags:
- Version Control
- FTP
- IDE
comments:
- id: 100
  author: Will Hamill
  author_email: ''
  author_url: http://twitter.com/willhamill
  date: '2012-01-13 19:06:00 +0000'
  date_gmt: '2012-01-13 18:06:00 +0000'
  content: Given how simple the good, free build/deployment solutions are, it's scandalous
    not to be using them. Have everything you do in version control, and have the
    build server kick off a new build/test/deploy cycle every time anything is submitted.
    This way you don't overwrite config and lose the file, you don't deploy code that
    doesn't pass tests, and you don't have any boring monotonous work to do besides
    committing code after it's saved in a working state. People shouldn't be either
    writing directly from IDE to deployment environment, or having to do some tedious
    extra manual steps. And obviously everything involved with the solution, from
    code through to config, should be stored in version control. Taking the bit of
    time required to get it set up saves a lot of time and a lot of tears later on
    - no losing config files, no manual upload steps and certainly no deployment of
    code that doesn't pass tests. Anything else is setting yourself up for problems!
---
<p>I have recently been getting more and more worried about people using FTP on projects that go anywhere near me.</p>
<p>It isn't that I have anything particularly against the protocol, over the years it has served me well and it still continues to do so when I have the need to use it, but FTP (especially the type tied into most IDEs) can lead you down some pretty scary alleyways on the way to FFFFFUUUUUUU-ville. Here are a couple of things that can happen, I am sure you can think of more;</p>
<ul>
<li>You can overwrite a file you didn't mean to overwrite.</li>
<li>You can upload information you don't really need to upload (an entire directory, for instance)</li>
<li>You can delete a file locally that will never be deleted on the server.</li>
</ul>
<p>Overwriting a file you didn't mean to can cause a lot of headaches - I am sure I am not the only one who has uploaded an incorrect config file in their time and then crapped themselves when the database suddenly won't connect. With something like version control the headache is mitigated by always being able to roll back, FTP however, not so much.</p>
<p>Uploading something you don't want to upload could be if you have a directory of thumbnails but you also have the originals images in them (bad practice, but I am sure it happens!). You upload the entire directory and you inadvertently upload extra information. To a lesser extent this can happen with things like the .svn folders that SVN leaves at its arse.</p>
<p>My final point is that deleting a file locally (in your IDE) does not then attempt to delete the linked file, or at least it doesn't in most of the IDEs I have used, this means that over the course of a project your webserver could become bloated with unnecessary files that could cause potential security risks and if nothing else will increase the size of any backup you take - potentially confusing people who need to access the files live on the server for whatever reason.</p>
<p>It is this last point that really has me worried, files being left on a server that people are maybe assuming are gone.</p>
<p>The old way of developing websites normally involved working on your files in some text editor, maybe testing them locally and then opening up your FTP client to transfer the files onto a dev or test server, then once you were happy you would transfer them from your local machine again onto a live environment.</p>
<p>This way of doing things just sucks, far too much human interaction, far too much scope for error and it is just boring.</p>
<p>The next step was for development environments to include FTP modules to allow you to automatically push code from your local machine to your development or live environment, this takes some of the human interaction out of the equation, but I think this is broken and dangerous.</p>
<p>IDEs have made us feel like there is less scope for error and have taken the monotony out of pushing data using FTP but I think with this relaxed process of uploading comes a relaxed process to how you handle your files and as I have already mentioned FTP is not brilliant at letting you recover from making sloppy mistakes.</p>
<p>Without firing up an FTP client and seeing on the one hand your local files and on the other your server's files you are less likely to notice when you are upload a load of images that maybe shouldn't be uploaded, or that certain server directories are full of files long since deleted on your local machine.</p>
<p>As I said at the start of this article, I do think FTP has served us well, and I think that FTP inside IDEs is a good idea for a couple of use cases, but it has made things too easy without giving us the safety net of something like a good version control system.</p>
<p>Of course the current best practice tends to be to use some form of version control coupled with some type of deployment solution and this is what I think people and companies should be doing (but that is an entirely different blog post for another night!)</p>
<p>If you are using FTP for the vast majority of your web project needs, I would urge you to research and consider other methods, I think it will lead to safer development and a happier you!</p>
