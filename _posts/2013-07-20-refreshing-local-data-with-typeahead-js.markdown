---
layout: post
status: publish
published: true
title: Refreshing local data with typeahead.js
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 1602
wordpress_url: http://tosbourn.com/?p=1602
date: '2013-07-20 10:59:40 +0100'
date_gmt: '2013-07-20 09:59:40 +0100'
categories:
- Development Help
tags:
- JavaScript
- Typeahead.js
- LocalStorage
- Prefetch
comments:
- id: 203
  author: Horace Li
  author_email: horaceli@gmail.com
  author_url: ''
  date: '2013-08-22 04:24:00 +0100'
  date_gmt: '2013-08-22 03:24:00 +0100'
  content: Thanks!
- id: 231
  author: Ravi Kumar
  author_email: visittoravi@gmail.com
  author_url: ''
  date: '2013-10-02 08:44:00 +0100'
  date_gmt: '2013-10-02 07:44:00 +0100'
  content: Great work.
- id: 245
  author: Guy Malachi
  author_email: guymal@gmail.com
  author_url: http://twitter.com/guy
  date: '2013-10-25 23:55:00 +0100'
  date_gmt: '2013-10-25 22:55:00 +0100'
  content: 'I''m trying to refresh the typeahead results but in my case there is one
    difference: I''m passing a name since I want to use localStorage. I''m doing the
    same as you described in your post and in addition I''m clearing the localStorage
    first. But typeahead is still taking the cached results from somewhere (after
    I clear localStorage, destroy the typeahead, and initialize it again). Any ideas?
    Thanks!'
- id: 251
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-10-26 11:47:00 +0100'
  date_gmt: '2013-10-26 10:47:00 +0100'
  content: |-
    Hey Guy,

    Thanks for your comment.

    Without seeing code it is hard to say for sure, but I would suggest when your Typeahead is getting updated you should give it a new name, maybe append a timestamp to the end of it or something, this should remove any caching effects.

    Hope that helps and let me know how you get on!
- id: 349
  author: moh.alzaeem
  author_email: moh.alzaeem@gmail.com
  author_url: ''
  date: '2013-12-27 19:46:00 +0000'
  date_gmt: '2013-12-27 18:46:00 +0000'
  content: Man i love you deeply, i was having a nightmare and you saved me.
- id: 350
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2013-12-27 21:09:00 +0000'
  date_gmt: '2013-12-27 20:09:00 +0000'
  content: Happy to help! :-D
- id: 367
  author: ashok kumar
  author_email: ashok.inspires@gmail.com
  author_url: ''
  date: '2014-01-08 12:32:00 +0000'
  date_gmt: '2014-01-08 11:32:00 +0000'
  content: Thanks Dude..
- id: 368
  author: ashok kumar
  author_email: ashok.inspires@gmail.com
  author_url: ''
  date: '2014-01-08 12:41:00 +0000'
  date_gmt: '2014-01-08 11:41:00 +0000'
  content: |-
    Yes, passing different names each time will work.


    its worked for me!
- id: 394
  author: acttrain
  author_email: burgis@activating-trainings.de
  author_url: ''
  date: '2014-01-25 19:12:00 +0000'
  date_gmt: '2014-01-25 18:12:00 +0000'
  content: "Sorry, I don´t understand it: \n\n   $('.example-twitter-oss .typeahead').typeahead({\n
    \   prefatch: 'link/typeahead/myTypeaheadRepo.json',\n    template: [\n      '{{language}}',\n
    \     '{{name}}',\n      '{{description}}'\n    ].join(''),\n    engine: Hogan\n
    \ });\n\nHaving something like this - how should I use your tip preventing refreshing
    issues?"
- id: 395
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-01-25 20:26:00 +0000'
  date_gmt: '2014-01-25 19:26:00 +0000'
  content: Glad you got it sorted :-)
- id: 421
  author: Bob Jones
  author_email: blahblah@aol.com
  author_url: ''
  date: '2014-03-03 20:02:00 +0000'
  date_gmt: '2014-03-03 19:02:00 +0000'
  content: 'TAHNK YOU!!! #1 was killing me too.'
- id: 589
  author: Atul Singh
  author_email: atulsolanki30@gmail.com
  author_url: ''
  date: '2014-09-12 07:34:00 +0100'
  date_gmt: '2014-09-12 06:34:00 +0100'
  content: how to refresh remote data please tell the way. i have urgent requirement
- id: 590
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-09-12 08:35:00 +0100'
  date_gmt: '2014-09-12 07:35:00 +0100'
  content: 'Remote data shouldn''t need refreshed, please share the code you have. '
- id: 591
  author: Atul Singh
  author_email: atulsolanki30@gmail.com
  author_url: ''
  date: '2014-09-12 09:03:00 +0100'
  date_gmt: '2014-09-12 08:03:00 +0100'
  content: "Thanks Toby for a quick reply.\n\nPlease find below code that i have written
    using widget i have used sleeted event so that i can store user selection and
    later submit the detail via post. This work fine for me. but as soon as i change
    my city from the form i need updated data where as its show me some cached data
    of different city.  \n\n '',\n                'id'=&gt;  'venue' ,        \n                'options'
    =&gt; ['placeholder' =&gt; 'Type a venue or restaurant name to map with'],\n                'scrollable'
    =&gt; true,\n                'pluginEvents' =&gt; [\n                'typeahead:selected'
    =&gt; \"function(e,datum) {\n                                            var array
    = $.map(datum, function(value, index) {\n                                                                        return
    [value];\n                                                                      });\n
    \                                       var reultString = array.toString();\n
    \                                       var resultArray = reultString.split(',');\n
    \                                       var id =  resultArray[1];\n                                    $('#selected_items').show();\n
    \                                   var radio = $(\"#w3 input[type='radio']:checked\").val();\n
    \                                   //radioTypeEst = document.getElementById('radioEstablishment').checked;\n
    \                                   //radioTypeVenue = document.getElementById('radioVenue').checked;\n
    \                                   if(radio != 4 &amp;&amp; radio != 1 &amp;&amp;
    radio != 2 &amp;&amp; radio != 3 ){\n                                       radio
    = 0;\n                                    }\n             \n             var maData
    = ''+$('#venue').val()+'&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href=\"void(0);\"
    rel=\"nofollow\">Delete</a>'\n             $('#selected_items').append(maData);\n
    \             $('#venue').val('');             \n\n             //$(this).data().term
    = null;\n             //$('.typeahead').typeahead('val', '');.\n           \n
    \   }\",\n   'typeahead:closed'=&gt;\"function(){ $('#venue').val('');}\",\n  ],
    \      \n                'pluginOptions' =&gt; ['highlight'=&gt;true,'minLength'=&gt;1],\n
    \       'dataset' =&gt; [\n                    [\n                        'remote'
    =&gt; Url::toRoute(['event/fetch-venue']). '?q=%QUERY',\n                        'templates'
    =&gt; [\n                          'empty' =&gt; 'Unable to find name for selected
    query.',\n                         ],\n                        \n                    ],\n
    \                   \n        ], \n            \n]);\n    ?&gt;\n\ni used changed
    event of city selection dropdown as below \n\n$('#eventsave-cityid').change(function()
    {\n     $('#venue').typeahead('destroy');\n     $('#venue').typeahead('initialize');\n
    \  \n     //venue_data_1.clearRemoteCache();\n     \n})\n\n\n\n\nPlease reply
    soon as it is urgent."
- id: 592
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-09-12 11:22:00 +0100'
  date_gmt: '2014-09-12 10:22:00 +0100'
  content: Hey - sorry I think stuff is missing from the code - could you paste it
    somewhere like jsbin.com and share?
- id: 611
  author: Atul Singh
  author_email: atulsolanki30@gmail.com
  author_url: ''
  date: '2014-09-14 08:00:00 +0100'
  date_gmt: '2014-09-14 07:00:00 +0100'
  content: please have a look on code. In brief the main problem is that how to reinitialize
    suggestion list for remote option so that when user change a city from drop down
    and type a letter it should pick from new city not from old city.  for more detail
    the code is here http://jsbin.com/xunexucoxeji/1/edit
- id: 612
  author: Toby Osbourn
  author_email: toby.osbourn@googlemail.com
  author_url: http://www.tosbourn.com/
  date: '2014-09-14 19:52:00 +0100'
  date_gmt: '2014-09-14 18:52:00 +0100'
  content: |-
    This post might help you: http://tosbourn.com/setting-a-minimum-length-for-your-search-in-typeahead-js/


    Especially the setting the minLength part :-)
- id: 615
  author: Atul Singh
  author_email: atulsolanki30@gmail.com
  author_url: ''
  date: '2014-09-15 13:11:00 +0100'
  date_gmt: '2014-09-15 12:11:00 +0100'
  content: Thanks a for reply.   I have solved this using replace option of typehead
    js. thus each time when a user enters a character the call goes to server.
- id: 635
  author: Anton Cakrabirawa
  author_email: franx47@yahoo.co.uk
  author_url: ''
  date: '2014-11-11 17:01:00 +0000'
  date_gmt: '2014-11-11 16:01:00 +0000'
  content: 'Thanks for this excellent code : $(''#item'').typeahead(''destroy'');'
- id: 647
  author: Daniel H.
  author_email: daniel@simbio.com.br
  author_url: ''
  date: '2014-12-16 13:31:00 +0000'
  date_gmt: '2014-12-16 12:31:00 +0000'
  content: thank you!
---
<p>If you are using local data or prefetched data with typeahead.js and you want to refresh that data there is a three step process you need to adhere to;</p>
<ol>
<li><span style="line-height: 14px;">Do not pass a name into your typeahead, doing so will initiate LocalStorage and your changes will not be registered.</span></li>
<li>When you want to refresh the data, you first need to destroy the current typeahead instance .typeahead('destroy') will accomplish this.</li>
<li>Next we need to recall typeahead with the updated local values or prefetched value.</li>
</ol>
<p>That first point is important and caused me a few headaches, hopefully upon reading this you will avoid those same headaches with typeahead.js</p>
<p>Here is a quick example;</p>
<pre><code>var items = ['aaa', 'bbb', 'ccc'];

$('#item').typeahead({
  local: items
});

$('#add_item').click(function() {
  items.push('ddd');
  $('#item').typeahead('destroy');
  $('#item').typeahead({
    local: items
  });
});</code></pre>
<p>Once <code>#add_item</code> is clicked, 'ddd' will be searchable.</p>
<p>This is taken from the <a title="Typeahead.js The Book!" href="http://tosbourn.com/2013/08/javascript/typeahead-js-the-book/">Instant Typeahead.js book</a> I have written.</p>
