---
layout: post
status: publish
published: true
title: Rspec's be_an_instance_of is pretty useful
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1597
wordpress_url: http://tosbourn.com/?p=1597
date: '2013-07-16 13:48:47 +0100'
date_gmt: '2013-07-16 12:48:47 +0100'
categories:
- Development Help
tags:
- Ruby
- Ruby on Rails
- Rspec
comments:
- id: 187
  author: David Chelimsky
  author_email: dchelimsky@gmail.com
  author_url: http://blog.davidchelimsky.net
  date: '2013-07-17 20:53:00 +0100'
  date_gmt: '2013-07-17 19:53:00 +0100'
  content: |-
    Hi Toby - I commented on this on [Reddit](http://www.reddit.com/r/ruby/comments/1ierwn/rspecs_be_an_instance_of_is_pretty_useful/), but in case you didn't see it or for anybody else who sees this post: RSpec does no such type conversion. If this is happening to you in a project that uses ActiveSupport, that is likely the source of the type conversion (see https://gist.github.com/dchelimsky/6023806).

    re:  `be_an_instance_of``, I agree that it is useful as an additional sanity check in this case because it solves a very specific problem you ran into, but I wouldn't recommend it generally because it creates additional noise and makes the code harder to change (consider that a decision to use Date instead of DateTime would require these examples changing).
- id: 188
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-07-17 23:08:00 +0100'
  date_gmt: '2013-07-17 22:08:00 +0100'
  content: |-
    Hi David,

    Thanks so much for commenting, I haven't looked at Reddit yet.

    That is very interesting that ActiveSupport is behind this, I (wrongly) assumed that anything after `.should` was in the Rspec realm, I will update the blog post accordingly.


    I totally agree that using `be_an_instance_of` couples your code a little too tightly, but then for most data types I would have thought that changing the type is going to cause some headaches in your test suite anyway.


    Thanks again, you have taught me a lot.
- id: 189
  author: Marcin Grzywaczewski
  author_email: killavus@gmail.com
  author_url: ''
  date: '2013-07-18 20:01:00 +0100'
  date_gmt: '2013-07-18 19:01:00 +0100'
  content: |-
    Hello.

    I think that using be_an_instance_of can be considered as smell.

    Ask yourself: "Why I need to have this DateTime object?".

    You want DateTime, because you want the public interface of DateTime. In such case, I would rather assert existence of methods (and maybe - output of these methods), not the particular class name. We code in a duck typed language, after all.
---
<p>Today I was testing a small helper method I had written that would convert a String to a date or if it was already a DateTime object it would just return it. A pretty simple function but one that needs testing all the same.</p>
<p>Initially my test looked something like this;</p>
<pre><code>
require 'spec_helper'
require 'date'
require 'time'

describe MyHelper do
  describe 'convert_to_datetime functionality' do

    let(:input) { '2012-03-04' }
    let(:date_version) { DateTime.parse(input) }

    it 'should successfully convert a well formatted date string' do
      output = convert_to_datetime input
      output.should == date_version
    end

    it 'should return the original date if a DateTime object was passed in' do
      output = convert_to_datetime date_version
      output.should == date_version
    end
  end
end
</code></pre>
<p>On the face of it this would seem to work, and indeed all the tests pass, but what if I changed <code>output.should == date_version</code> to <code>output.should == input</code>? Instant fail? Nope!</p>
<p>The reason why this also passes is because I am including ActiveSupport earlier on in the code and with that included so long as the String when converted to a DateTime is the same DateTime then <code>.should ==</code> will pass.</p>
<p>This was unexpected, but fortunately I very quickly found <code>be_an_instance_of</code>, what this allows us to do is check that a variable is an instance of a particular class, in our example a DateTime class.</p>
<p>Now my code reads;</p>
<pre><code>
require 'spec_helper'
require 'date'
require 'time'

describe MyHelper do
  describe 'convert_to_datetime functionality' do

    let(:input) { '2012-03-04' }
    let(:date_version) { DateTime.parse(input) }

    it 'should successfully convert a well formatted date string' do
      output = convert_to_datetime input
      output.should be_an_instance_of(DateTime)
      output.should == date_version
    end

    it 'should return the original date if a DateTime object was passed in' do
      output = convert_to_datetime date_version
      output.should be_an_instance_of(DateTime)
      output.should == date_version
    end
  end
end
</code></pre>
<p>Which is a more solid check.</p>
<p><strong>*Update*</strong></p>
<p>Some nice folk on <a href="http://www.reddit.com/r/ruby/comments/1ierwn/rspecs_be_an_instance_of_is_pretty_useful/">Reddit</a> pointed out that I could have done one of the following;</p>
<ol>
<li>Swapped <code>output.should</code> for <code>date_version.should</code> which would force rspec not to change my DateTime into a String.</li>
<li>Used <code>eql</code> instead of <code>==</code> which does not do type conversion.</li>
<li>Using be_instance_of can make your code a little harder to read and might end up coupling your test to a particular data type and if that changes you could end up with stuff to fix.</li>
</ol>
