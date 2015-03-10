---
layout: post
status: publish
published: true
title: Validation Helpers
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1347
wordpress_url: http://tosbourn.com/?p=1347
date: '2013-03-12 22:52:41 +0000'
date_gmt: '2013-03-12 21:52:41 +0000'
categories:
- Development Help
tags:
- Ruby
- Ruby on Rails
comments: []
---
<p>Here is a list of some of the common validation helpers in Ruby on Rails;</p>
<ul>
<li>validates_acceptance_of</li>
<li>validates_associated</li>
<li>validates_confirmation_of</li>
<li>validates_each</li>
<li>validates_exclusion_of</li>
<li>validates_format_of</li>
<li>validates_inclusion_of</li>
<li>validates_length_of</li>
<li>validates_numericality_of</li>
<li>validates_presence_of</li>
<li>validates_uniqueness_of</li>
</ul>
<p><strong>validates_acceptance_of</strong> is used to see if someone has checked a checkbox during a form submission, the attribute does not need to have an associated database column.</p>
<p><strong>validates_associated</strong> is used to see if the objects you are associating with your model are valid objects.</p>
<p><strong>validates_confirmation_of</strong> is used when confirming things like passwords the convention is that you would confirm the attribute password against the attribute password_confirm.</p>
<p><strong>validates_each</strong> is used to validate attributes against a block of code.</p>
<p><strong>validates_exclusion_of</strong> is used to validate if an attribute is not in a particular enumerable object.</p>
<p><strong>validates_format_of</strong> is used to validate the format of an attribute. This is handled with a regular expression and can be used to make sure a pattern does not exist within the attribute.</p>
<p><strong>validates_inclusion_of</strong> is used basically as the opposite of exclusion, it makes sure the attribute is found within an enumerable object.</p>
<p><strong>validates_length_of</strong> is used to verify that the length of the attribute matches the restrictions that have been put in place around it.</p>
<p><strong>validates_numericality_of</strong> is used to ensure something is a number and can go as far to say a number greater than or less than something, or force it to only be an integer.</p>
<p><strong>validates_presence_of</strong> is used to ensure that the attribute exists and is not nil when it is being saved.</p>
<p><strong>validates_uniqueness_of</strong> is used to ensure that there are no other attributes with the same information in the system.</p>
<p>I hope this helps someone as an uber quick reference.</p>
<p>&nbsp;</p>
