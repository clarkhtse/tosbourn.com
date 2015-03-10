---
layout: post
status: publish
published: true
title: Converting numbers to hex using to_s in Ruby
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2345
wordpress_url: http://tosbourn.com/?p=2345
date: '2014-09-25 13:21:48 +0100'
date_gmt: '2014-09-25 12:21:48 +0100'
categories:
- Development Help
tags:
- Ruby
comments: []
---
<p>Today I learned that you can easily convert a number to its hex value by calling to_s on it along with the base you want to convert as a parameter on to_s.</p>
<pre>170.to_s(16)
 =&gt; "aa"
</pre>
<p>Of course this means you can also convert it to binary (base 2)</p>
<pre>170.to_s(2)
 =&gt; "10101010"
</pre>
<p>Personally I like my hexadecimals to be in uppercase, I could call <code>to_s(16).upcase</code> each time but that feels a little wasteful, why don't we make a method to do that for us?</p>
<pre>class Numeric
   def to_hex
      to_s(16).upcase
   end
end</pre>
<p>My use case for this was to convert RGB values to Hex values, now generally when you do that you would want an RGB value of 0,0,0 to be converted into 000000, but as you can will calling to_hex on 0 currently produces 0.</p>
<pre>0.to_hex
 =&gt; "0"
</pre>
<p>How do we change this? The method I went for was to pad my output after changing it to a string.</p>
<pre>0.to_hex.rjust(2, '0')
 =&gt; "00"
</pre>
