---
layout: post
status: publish
published: true
title: Managing a Facebook development project.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 614
wordpress_url: http://tosbourn.com/?p=614
date: '2011-10-15 18:26:56 +0100'
date_gmt: '2011-10-15 17:26:56 +0100'
categories:
- Development Help
tags:
- Development
- Facebook
comments:
- id: 255
  author: Cygnis Media
  author_email: clark@cygnismedia.com
  author_url: http://www.cygnismedia.com/social-media-application/facebook-developer.html
  date: '2013-10-29 11:02:00 +0000'
  date_gmt: '2013-10-29 10:02:00 +0000'
  content: |-
    Very hard to manage so many apps, but we are using differen Facebook Developers accounts.

    Regards:
    http://www.cygnismedia.com/
---
<p><a href="http://tosbourn.com/wp-content/uploads/2011/10/facebookdevelopers.png"><img class="alignright size-medium wp-image-616" title="facebookdevelopers" src="http://tosbourn.com/wp-content/uploads/2011/10/facebookdevelopers-300x197.png" alt="" width="300" height="197" /></a>Recently in work we hit an issue where we needed access to an historic customised Facebook page.  We had access to the code but not access to admin section of the Facebook App.</p>
<p>I am sure we aren't the only company this has happened to, so I figured I would write some thoughts on how I think this should best be handled.  For the sake of brevity I will only discuss how developers should be managed, I will ignore testers or anyone else for now, I will also only be talking about looking after the Facebook App on Facebook, not the development work behind the scenes.</p>
<p>Facebook Apps carry with them the notion of roles, currently there are 5 of them, which you can read more about in the <a href="http://developers.facebook.com/docs/ApplicationSecurity/" target="_blank">Application Security section of the Facebook Developer Documentation</a>. For the purposes of what I am discussing today we are only really interested in the <strong>Administrator role</strong> and the <strong>Developer Role</strong>.</p>
<p>The difference between these roles is basically that Developers can't add others to the App or reset / delete information about the App whilst administrators can.</p>
<p>The other thing that Facebook Apps carry with them is a (new) notion of <a href="http://developers.facebook.com/blog/post/531" target="_blank">Groups</a>, this allows you to assign multiple users to a group and then assign the group to specific roles within the App.</p>
<p>Armed with these ideas my solution is very simple, first you need to set up two groups;</p>
<ul>
<li>Senior Developers</li>
<li>Developers</li>
</ul>
<p>Unless you have a massive development team I would suggest keeping the Senior Developer group for one or two people who will be in charge of creating new Facebook Apps and administering them.  They don't even need to be technical people, but I think they should be someone who it is generally accepted has a long future with the company.</p>
<p>All other developers that need to look at Facebook Apps should go into the Developers group (including anyone listed as a Senior Developer).</p>
<p>Then for each App you should assign the Senior Developer group the role of Administrator, and the Developer group the role of Developer.  Facebook requires that at least one actual person be kept as Administrator, I would suggest maybe a business manager role for this.</p>
<p>So long as both groups are kept up to date administering the access of individual Apps will be a breeze, just add new developers when they join and remove them when they leave.  The Senior Developer role is slightly trickier only because if you have two and they both leave around the same time you will need someone outside of the 'Facebook team' to remind them to appoint new users to the group.</p>
<p>That is really all there is to it.  Would love to hear your thoughts on how you manage it yourself.</p>
<p style="text-align: right;"><strong>Last edited 18/10/2011<br />
Added in information about needing one actual user in the admin field.<br />
</strong></p>
