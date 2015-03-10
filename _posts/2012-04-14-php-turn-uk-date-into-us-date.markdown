---
layout: post
status: publish
published: true
title: PHP - Turn UK Date into US Date
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 969
wordpress_url: http://tosbourn.com/?p=969
date: '2012-04-14 11:34:34 +0100'
date_gmt: '2012-04-14 10:34:34 +0100'
categories:
- Development Help
tags:
- PHP
- Github
- Dates
- US
- UK
comments: []
---
<p>This is something I find myself needing to do quite frequently. You deal with UK dates as input and output of a system but somewhere in the middle they need to convert to US dates.</p>
<p>A quick way to shove a UK Date into a US format is to to an explode on the UK date by whichever separator it is using (normally '/', sometimes '-') then glue the bits back together with the second element swapped with the first (moving month and day around).</p>
<p>I have compiled this into a quick method:</p>
<pre>/**
* A very simple function to change the date from the UK
* format to the American format.
*
* @param string $uk_date Assumed to be in the format day month year
* @param string $separator_input What divides the date up goung in.
* @param string $sepatator_output What divides the date up going out.
*
* @return string The date formatted to suit the US formatting.
*
* @author Toby Osbourn 
*/

function makeUSDate($uk_date, $separator_input = '/', $sepatator_output = '/')
{
    list($day, $month, $year) = explode($separator_input, $uk_date);
    return $month.$sepatator_output.$day.$sepatator_output.$year;
}</pre>
<p>This is also part of my <a href="https://github.com/tosbourn/Useful-PHP-Functions">Useful PHP Functions</a> file on Github.</p>
