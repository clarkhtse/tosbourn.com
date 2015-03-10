---
layout: post
status: publish
published: true
title: Less Than Vs Less Than or Equal To - which is more efficient?
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 569
wordpress_url: http://tosbourn.com/?p=569
date: '2011-09-24 23:29:12 +0100'
date_gmt: '2011-09-24 22:29:12 +0100'
categories:
- Other
tags:
- PHP
- Optimise
comments: []
---
<p>When dealing with integer values we all know that $x &lt; 2 has the same number of possibilities as $x &lt;= 1.</p>
<p>Occasionally there will be a semantic reason why someone should chose the less than symbol or if they should use less than or equal to, but I was wondering if in the cases when you know the values being compared are both integers and there is no inherent semantic reason why one is more appropriate which is the most efficient to use.</p>
<p>I decided to perform a test using two very similar bits of code, one was designed to iterate over a for loop 100 million times using less than or equals to and the other would be modified to just use less than.</p>
<h2>Test environment:</h2>
<p>I was running these scripts from the command line on my Macbook Pro, these are the specs;</p>
<pre>Model Name:	        MacBook Pro
Model Identifier:	MacBookPro8,1
Processor Name:	        Intel Core i5
Processor Speed:	2.3 GHz
Number of Processors:	1
Total Number of Cores:	2
L2 Cache (per Core):	256 KB
L3 Cache:	        3 MB
Memory:	                4 GB</pre>
<p>The PHP version is 5.3.6</p>
<h2>The Code:</h2>
<p>Here are the two snippets of code I ran, nothing fancy, but if you want to test my results for yourself please run this code as is without any changes at all, just to ensure consistency.</p>
<p>Less Than or Equal To:<br />
{code type=PHP}<br />
&lt;?PHP<br />
$start = microtime(true);<br />
echo "Less than or equal to done 100 million times. \n";<br />
echo "Start: $start \n";<br />
for ($i = 0; $i &lt;= 100000000; $i++) {<br />
$x = 1 + $i;<br />
}<br />
$end = microtime(true);<br />
echo "End: $end \n";<br />
echo "Difference: ".($end - $start);<br />
?&gt;<br />
{/code}</p>
<p>Less Than:<br />
{code type=PHP}<br />
&lt;?PHP<br />
$start = microtime(true);<br />
echo "Less than done 100 million times. \n";<br />
echo "Start: $start \n";<br />
for ($i = 0; $i &lt; 100000001; $i++) {<br />
$x = 1 + $i;<br />
}<br />
$end = microtime(true);<br />
echo "End: $end \n";<br />
echo "Difference: ".($end - $start);<br />
?&gt;<br />
{/code}</p>
<h2>The Results:</h2>
<p>Before I give my results I should state my opinion, I figured that just less than would be more efficient, as there is only one comparison to do.  I am not sure how PHP boils down those operations and how the <acronym title="Arithmetic Logic Unit">ALU</acronym> will eventually deal with them, but I would guess that less than or equals to isn't going to have it's own function, probably more a combination of functions.</p>
<p>I ran the above code several times each at 3 different times throughout the day but didn't want to display the entire table so took the average at each sampling time and used it;</p>
<table>
<caption>100 million iterations of less than or equals to</caption>
<tbody>
<tr>
<th>Iteration</th>
<th>Microtime Difference</th>
</tr>
<tr>
<td>1</td>
<td>6.6050539016724</td>
</tr>
<tr>
<td>2</td>
<td>6.5961098670959</td>
</tr>
<tr>
<td>3</td>
<td>6.5776059627533</td>
</tr>
<tr>
<td>Average</td>
<td>6.59292324384053</td>
</tr>
</tbody>
</table>
<table>
<caption>100 million iterations of just less than</caption>
<tbody>
<tr>
<th>Iteration</th>
<th>Microtime Difference</th>
</tr>
<tr>
<td>1</td>
<td>6.4923448562622</td>
</tr>
<tr>
<td>2</td>
<td>6.4607081413269</td>
</tr>
<tr>
<td>3</td>
<td>6.8488190174103</td>
</tr>
<tr>
<td>Average</td>
<td>6.6006240049998</td>
</tr>
</tbody>
</table>
<h2>Conclusions:</h2>
<p>Just comparing the averages would indicate that my assumption was wrong, but I think considering the for loop was iterating 100 million times and the fact that the overall difference between the two bits of code was 0.00770076115927 seconds the real conclusion to be drawn here is that it just doesn't matter.</p>
<p>Since there is seemingly no performance gain to be had in PHP when using either less than or less than or equal to then I would suggest using your own personal preference.</p>
<p>I guess if you were to consider the code size of the .php file, there is one character less needed for less than, but if you are looking to optimise code by removing single characters in order to reduce the size overhead, you are already dealing with some pretty damn well optimised code!</p>
