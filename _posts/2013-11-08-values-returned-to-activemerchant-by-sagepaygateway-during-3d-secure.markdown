---
layout: post
status: publish
published: true
title: Values returned to ActiveMerchant by SagePayGateway during 3d secure
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1735
wordpress_url: http://tosbourn.com/?p=1735
date: '2013-11-08 16:13:40 +0000'
date_gmt: '2013-11-08 15:13:40 +0000'
categories:
- Development Help
tags:
- SagePay
- 3D Secure
comments: []
---
<p>When you are getting values returned back to you by SagePay's payment Gateway during a successful 3D Secure authentication your system will be hit with a POST that contains the following keys;</p>
<ul>
<li>PaRes</li>
<li>MD</li>
<li>MDX</li>
</ul>
<p>In order to tie these back into your system you should check the order against the PaRes value that you sent to the 3D Secure provider.</p>
<p>&nbsp;</p>
