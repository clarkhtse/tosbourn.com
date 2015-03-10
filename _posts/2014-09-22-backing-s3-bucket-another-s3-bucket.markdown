---
layout: post
status: publish
published: true
title: Backing up an s3 bucket to another s3 bucket
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2343
wordpress_url: http://tosbourn.com/?p=2343
date: '2014-09-22 14:05:56 +0100'
date_gmt: '2014-09-22 13:05:56 +0100'
categories:
- Development Help
tags: []
comments:
- id: 617
  author: Mike Fiedler
  author_email: miketheman@gmail.com
  author_url: http://www.miketheman.net/
  date: '2014-09-23 13:32:00 +0100'
  date_gmt: '2014-09-23 12:32:00 +0100'
  content: |-
    Curious - does the sync command have to download each object locally before transferring the object to the new bucket?

    We recently looked at doing something similar, as we were experimenting with the contents of a bucket, and found that using the S3 Object Versioning actually made most sense. Did this option arise, or are there drawbacks to using it?

    http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectVersioning.html
- id: 618
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-09-23 13:50:00 +0100'
  date_gmt: '2014-09-23 12:50:00 +0100'
  content: |-
    Hey Mike,


    Thanks so much for the comment.


    I had looked into Object Versioning, but our needs were very simple, we just wanted a like for like backup of files that we would likely be dumping after making the changes we needed.


    The sync command doesn't appear to download, and the speed is much faster than I would have assumed for some largish files.
- id: 619
  author: Mike Fiedler
  author_email: miketheman@gmail.com
  author_url: http://www.miketheman.net/
  date: '2014-09-25 23:11:00 +0100'
  date_gmt: '2014-09-25 22:11:00 +0100'
  content: |-
    I was curious about the speed, and dug into the s3cmd source, and found out how they are awesomely sneaky.

    In your s3cmd scenario, since the prefix of both the source and destination begin with `s3://`, the method `cmd_sync_remote2remote` is invoked, and the `_upload` method inside of that is called.
    https://github.com/s3tools/s3cmd/blob/25ff338b31b9d6be06ab80a754ff1edfb1ef88c8/s3cmd#L895-L900

    The _upload calls a method named `object_copy` that appears to do some nifty HTTP header stuff, preventing the need for the object to come down the wire to the local machine.
    https://github.com/s3tools/s3cmd/blob/25ff338b31b9d6be06ab80a754ff1edfb1ef88c8/S3/S3.py#L606-L629

    Finally, the COPY directive and headers are explained here: http://docs.aws.amazon.com/AmazonS3/latest/API/RESTObjectCOPY.html

    This is a cool feature in s3cmd, will definitely remember it for next time.
- id: 622
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-09-29 09:28:00 +0100'
  date_gmt: '2014-09-29 08:28:00 +0100'
  content: That is some great follow up, thanks so much Mike! Very useful.
---
<p>In a project I am working on in <a href="http://rumblelabs.com">Rumble Labs</a> we had cause to want to backup an entire s3 bucket before making potentially destructive changes.</p>
<p>After some research I found that AWS have an officially supported client that would allow you to do just this. In this guide I will walk you through how to install the AWS client, create a new bucket and sync your stuff across to this new bucket.</p>
<h2>Installing and Configuring AWS CLI</h2>
<p>I had both Python and Pip installed so was able to install everything using Pip with the following command</p>
<pre>sudo pip install awscli</pre>
<p>If you don't have Pip installed you can <a href="http://pip.readthedocs.org/en/latest/installing.html">follow this guide</a>.</p>
<p>Now we need to configure our AWS client by giving it our keys and such, this is explained in full in the <a href="http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html">official guide</a> but all I needed to do was run the following command</p>
<pre>aws configure</pre>
<p>You will be asked a series of questions;</p>
<ul>
<li>Access Key (required)</li>
<li>Secret Key (required)</li>
<li>Default Region (I left this blank)</li>
<li>Default Output format (I left this blank)</li>
</ul>
<p>You can run the configure command as many times as you like, any blank answers will assume the previous setting is staying unchanged.</p>
<h2>Backing up your s3 Bucket</h2>
<p>The first thing we want to do is create a new bucket to house our backup</p>
<pre>aws s3 mb s3://my-backup-bucket</pre>
<p>What this does is tell aws that we are performing an s3 related action, the action we are performing is mb (make bucket) and we are supplying a bucket name, in this case my-backup-bucket.</p>
<p>Now we have everything in place to copy our stuff into our new bucket, we do this with the <code>aws sync</code> command</p>
<pre>aws s3 sync s3://my-current-bucket s3://my-backup-bucket</pre>
<p>What this does is tell aws again that we are performing an s3 action, this time we are performing the sync action. This action takes two properties, the bucket we are copying from and the bucket we are copying to.</p>
<p>Once you run this you will receive the output of the files copying in your terminal, which I wanted because I like to keep an eye on these things. If you don't want to see this I see there is a <code>--quiet</code> flag listed in the <a href="http://docs.aws.amazon.com/cli/latest/reference/s3/sync.html">documentation for sync</a>.</p>
