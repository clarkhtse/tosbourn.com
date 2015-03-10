---
layout: post
status: publish
published: true
title: Force a CSV download from a WordPress Plugin
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2340
wordpress_url: http://tosbourn.com/?p=2340
date: '2014-09-16 23:24:26 +0100'
date_gmt: '2014-09-16 22:24:26 +0100'
categories:
- Development Help
tags:
- Wordpress
- Download
- CSV
comments: []
---
<p>If you are writing a WordPress Plugin and want to automatically download a CSV file when a certain page is hit here is roughly how you go about it.</p>
<p>All this code can sit in your main plugin file, or however you like to organise your plugins.</p>
<pre><code>

// Standard code to add a menu item in the admin section
function my_menu() {
    add_menu_page('Download CSV', 'Download CSV', 'add_users', 'my_csv_download', 'csv_download');

}

// Important - Note this is not stored in a function, this is just in the main
// file, if we ran it through a function headers would already get set.
if (isset($_GET['page']) &amp;&amp; $_GET['page'] === 'my_csv_download') {
    // Just setting some headers for our download
    header("Pragma: public");
    header("Expires: 0");
    header("Cache-Control: must-revalidate, post-check=0, pre-check=0");
    header("Cache-Control: private", false);
    header("Content-Type: application/octet-stream");
    header("Content-Disposition: attachment; filename=\"my_csv.csv\";" );
    header("Content-Transfer-Encoding: binary");
    echo csv(); // Your CSV goes here.
    exit;
}

// This action adds our menu to the main menu structure
add_action('admin_menu', 'my_menu');
</code></pre>
