---
layout: post
status: publish
published: true
title: Removing "Protected:" and "Private:" from WordPress posts
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2093
wordpress_url: http://tosbourn.com/?p=2093
date: '2014-07-06 14:30:16 +0100'
date_gmt: '2014-07-06 13:30:16 +0100'
categories:
- Development Help
tags:
- Wordpress
comments: []
---
<p>By default WordPress will prepend the copy "Protected: " to any post title that is protected by a password and will prepend the copy "Private: " to any post title that is set as a private post.</p>
<p>I can see the sense in doing this, in a lot of cases you want to clearly mark those posts as such. In my use case though I am helping theme a site for a <a href="http://www.weddingphotographerlisburn.co.uk/" target="_blank">photographer</a>, and all his client photos are password protected, in this case having the extra "Protected" copy just looks ugly.</p>
<p>Happily there is a really simple fix you can apply to kill this wording, add the following snippet to your theme's <code>functions.php</code> file.</p>
<pre><code>
function protect_my_privates($text){
  $text='%s';
  return $text;
}
add_filter('private_title_format','protect_my_privates');
add_filter('protected_title_format', 'protect_my_privates');
</code></pre>
<p>What this does is tells both <code>private_title_format</code> and <code>protected_title_format</code> that we just want to pass through the title and not append or prepend anything to it.</p>
<p>If you did want to do something special to the text you could always edit <code>$text</code> to be something like;</p>
<pre><code>
$text = '[protected]%s[/protected]'
</code></pre>
<p>This will make a title that is called "Hello World" appear like "[protected]Hello World[/protected]"</p>
