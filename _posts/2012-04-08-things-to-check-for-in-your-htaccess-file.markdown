---
layout: post
status: publish
published: true
title: Things to check for in your htaccess file
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 898
wordpress_url: http://tosbourn.com/?p=898
date: '2012-04-08 19:40:19 +0100'
date_gmt: '2012-04-08 18:40:19 +0100'
categories:
- Development Help
tags:
- htaccess
comments: []
---
<p>Obviously everyone needs .htaccess files for different reasons, but over the years I have noted a few things that generally seem to sneak themselves in - so I decided to draw up a list of things you might want to consider before go live on a site that relate just to .htaccess files.</p>
<p>A good lot of these are covered by the <a href="http://html5boilerplate.com/">HTML5 Boilerplate</a>, so if you are looking for a quick win you could always download it.</p>
<p>The tl;dr version is this quick list:</p>
<ul>
<li><strong>Redirect to www</strong></li>
<li><strong>Comments</strong></li>
<li><strong>Forcing latest version of IE</strong></li>
<li><strong>Gzip compression</strong></li>
<li><strong>Setting some expires headers</strong></li>
<li><strong>Custom Error Pages</strong></li>
<li><strong>Block access to certain file types</strong></li>
</ul>
<h2>Redirect to www</h2>
<p>A very common requirement for .htaccess is to redirect non-www traffic to the www. domain (or vice versa) .</p>
<p>This keeps traffic on your website consistent (which can be invaluable when trying to debug issues or gather statistics).</p>
<p>Here is the code you would need.</p>
<pre>RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule ^ http://www.%{HTTP_HOST}%{REQUEST_URI} [L,R=301]</pre>
<h2>Comments</h2>
<p>This will sound like a weird one, but I know a lot of programmers who comment absolutely everything but will never comment .htaccess files.</p>
<p>A quick comment can outline what you are intending various lines to do, which will save you a lot of angst in the long run, especially if your htaccess file is doing something non-trivial or mission critical.</p>
<p>Comments are created by starting a line with the # character.  The rest of the line will then be ignored.</p>
<p>Here is a sample of a comment.</p>
<pre>#The following redirects traffic to https, do not delete it.</pre>
<h2>Forcing the latest version of IE</h2>
<p>We can do this in a couple of ways, but this is a nice quick way to easily apply the fix for IE. As well as forcing the latest version of IE it will also use the ChromeFrame if it is available.</p>
<p>This doesn't need to be set for certain files, so we can exclude them.</p>
<pre>&lt;IfModule mod_headers.c&gt;
Header set X-UA-Compatible "IE=Edge,chrome=1"
&lt;FilesMatch "\.(js|css|gif|png|jpe?g|pdf|xml|oga|ogg|m4a|ogv|mp4|m4v|webm|svg|svgz|eot|ttf|otf|woff|ico|webp|appcache|manifest|htc|crx|oex|xpi|safariextz|vcf)$" &gt;
Header unset X-UA-Compatible
&lt;/FilesMatch&gt;
&lt;/IfModule&gt;</pre>
<h2>Gzip Compression</h2>
<p>If possible we should try and compress anything coming from the webserver, it will help to make your website feel more snappy and save you some bandwidth.</p>
<pre>&lt;IfModule mod_deflate.c&gt;
&lt;IfModule mod_setenvif.c&gt;
&lt;IfModule mod_headers.c&gt;
SetEnvIfNoCase ^(Accept-EncodXng|X-cept-Encoding|X{15}|~{15}|-{15})$ ^((gzip|deflate)\s*,?\s*)+|[X~-]{4,13}$ HAVE_Accept-Encoding
RequestHeader append Accept-Encoding "gzip,deflate" env=HAVE_Accept-Encoding
&lt;/IfModule&gt;
&lt;/IfModule&gt;</pre>
<pre>&lt;IfModule filter_module&gt;
FilterDeclare   COMPRESS
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/html
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/css
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/plain
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/xml
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/x-component
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/javascript
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/json
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/xml
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/xhtml+xml
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/rss+xml
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/atom+xml
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/vnd.ms-fontobject
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $image/svg+xml
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $image/x-icon
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/x-font-ttf
FilterProvider  COMPRESS  DEFLATE resp=Content-Type $font/opentype
FilterChain     COMPRESS
FilterProtocol  COMPRESS  DEFLATE change=yes;byteranges=no
&lt;/IfModule&gt;

&lt;IfModule !mod_filter.c&gt;
AddOutputFilterByType DEFLATE text/html text/plain text/css application/json
AddOutputFilterByType DEFLATE application/javascript
AddOutputFilterByType DEFLATE text/xml application/xml text/x-component
AddOutputFilterByType DEFLATE application/xhtml+xml application/rss+xml application/atom+xml
AddOutputFilterByType DEFLATE image/x-icon image/svg+xml application/vnd.ms-fontobject application/x-font-ttf font/opentype
&lt;/IfModule&gt;
&lt;/IfModule&gt;</pre>
<h2>Setting some expires headers</h2>
<p>There are a lot of files that should be cached at the earliest possible time by the browser to save them having to be downloaded several times.</p>
<p>The code to do this looks pretty verbose but covers most angles.</p>
<pre>&lt;IfModule mod_expires.c&gt;
ExpiresActive on
ExpiresDefault                          "access plus 1 month"
ExpiresByType text/cache-manifest       "access plus 0 seconds"
ExpiresByType text/html                 "access plus 0 seconds"
ExpiresByType text/xml                  "access plus 0 seconds"
ExpiresByType application/xml           "access plus 0 seconds"
ExpiresByType application/json          "access plus 0 seconds"
ExpiresByType application/rss+xml       "access plus 1 hour"
ExpiresByType application/atom+xml      "access plus 1 hour"
ExpiresByType image/x-icon              "access plus 1 week"
ExpiresByType image/gif                 "access plus 1 month"
ExpiresByType image/png                 "access plus 1 month"
ExpiresByType image/jpg                 "access plus 1 month"
ExpiresByType image/jpeg                "access plus 1 month"
ExpiresByType video/ogg                 "access plus 1 month"
ExpiresByType audio/ogg                 "access plus 1 month"
ExpiresByType video/mp4                 "access plus 1 month"
ExpiresByType video/webm                "access plus 1 month"
ExpiresByType text/x-component          "access plus 1 month"
ExpiresByType application/x-font-ttf    "access plus 1 month"
ExpiresByType font/opentype             "access plus 1 month"
ExpiresByType application/x-font-woff   "access plus 1 month"
ExpiresByType image/svg+xml             "access plus 1 month"
ExpiresByType application/vnd.ms-fontobject "access plus 1 month"
ExpiresByType text/css                  "access plus 1 week"
ExpiresByType application/javascript    "access plus 1 week"
&lt;/IfModule&gt;</pre>
<h2>Custom Error Pages</h2>
<p>Custom Error Pages are an excellent way to customise your site, for example if your site returns a 404 error instead of showing the default page sent from Apache.</p>
<p>This is a pretty small bit of code.</p>
<pre>ErrorDocument 404 /404.html</pre>
<p>All this means is for the Error Document called 404, send the user to the page 404.html</p>
<h2>Block access to certain file types</h2>
<p>Oftentimes various text editors and programs will leave files that just end up getting uploaded with the other files when you update your website - best practice would be to not put these files on your web server but sometimes this cannot be avoided, and regardless of why they are there you should do something to tidy them up.</p>
<p>The following code blocks access to various files.</p>
<pre>&lt;FilesMatch "(\.(bak|config|sql|fla|psd|ini|log|sh|inc|swp|dist)|~)$"&gt;
Order allow,deny
Deny from all
Satisfy All
&lt;/FilesMatch&gt;</pre>
<h2>Conclusion</h2>
<p>There are plenty of other things .htaccess files can do, but these are the things I personally use most often, I hope you find them as useful as I have.</p>
<p>If there are things you think I should be adding to this list please share in the comments.</p>
