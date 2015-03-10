---
layout: post
status: publish
published: true
title: Skipfish - No such file or directory.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 252
wordpress_url: http://www.tosbourn.com/?p=252
date: '2010-05-21 22:57:59 +0100'
date_gmt: '2010-05-21 21:57:59 +0100'
categories:
- Development Help
tags:
- Google
- Security
- Skipfish
- Ubuntu
comments:
- id: 165
  author: Seb
  author_email: runje@free.fr
  author_url: ''
  date: '2013-06-18 13:39:00 +0100'
  date_gmt: '2013-06-18 12:39:00 +0100'
  content: Thanks for sparing me a headache, thanks !
- id: 166
  author: Seb
  author_email: runje@free.fr
  author_url: ''
  date: '2013-06-18 13:39:00 +0100'
  date_gmt: '2013-06-18 12:39:00 +0100'
  content: Thanks for sparing me a headache, thanks !
- id: 216
  author: igo
  author_email: asd@dsad.com
  author_url: ''
  date: '2013-09-23 13:23:00 +0100'
  date_gmt: '2013-09-23 12:23:00 +0100'
  content: |-
    this one might be missing too

    sudo apt-get install libpcre3-dev
---
<p>I wanted to play about with Google's <a href="http://code.google.com/p/skipfish/">Skipfish</a> to see if it could automate any of my security scans and grabbed the source code from the code library.</p>
<p>When I tried to make the file whilst running Ubuntu 9.10 I was presented with the following error:</p>
<p><code>cc -L/usr/local/lib/ -L/opt/local/lib skipfish.c -o skipfish -O3 -Wno-format -Wall -funsigned-char -g -ggdb -I/usr/local/include/ -I/opt/local/include/ -D_FORTIFY_SOURCE=0 \<br />
http_client.c database.c crawler.c analysis.c report.c -lcrypto -lssl -lidn -lz<br />
In file included from crawler.h:26,<br />
from skipfish.c:39:<br />
http_client.h:26:25: error: openssl/ssl.h: No such file or directory<br />
In file included from crawler.h:26,<br />
from skipfish.c:39:<br />
http_client.h:189: error: expected specifier-qualifier-list before ‘SSL_CTX’<br />
skipfish.c: In function ‘main’:<br />
skipfish.c:154: warning: implicit declaration of function ‘SSL_library_init’<br />
http_client.c:37:25: error: openssl/ssl.h: No such file or directory<br />
http_client.c:38:25: error: openssl/err.h: No such file or directory<br />
http_client.c:39:18: error: idna.h: No such file or directory<br />
http_client.c:40:18: error: zlib.h: No such file or directory<br />
In file included from database.h:29,<br />
from http_client.c:45:<br />
http_client.h:189: error: expected specifier-qualifier-list before ‘SSL_CTX’<br />
http_client.c: In function ‘parse_url’:<br />
http_client.c:285: warning: implicit declaration of function ‘idna_to_ascii_8z’<br />
http_client.c:285: error: ‘IDNA_SUCCESS’ undeclared (first use in this function)<br />
http_client.c:285: error: (Each undeclared identifier is reported only once<br />
http_client.c:285: error: for each function it appears in.)<br />
http_client.c: In function ‘parse_response’:<br />
http_client.c:1516: error: ‘z_stream’ undeclared (first use in this function)<br />
http_client.c:1516: error: expected ‘;’ before ‘d’<br />
http_client.c:1521: error: ‘d’ undeclared (first use in this function)<br />
http_client.c:1531: warning: implicit declaration of function ‘inflateInit2’<br />
http_client.c:1531: error: ‘Z_OK’ undeclared (first use in this function)<br />
http_client.c:1532: warning: implicit declaration of function ‘inflateEnd’<br />
http_client.c:1537: warning: implicit declaration of function ‘inflate’<br />
http_client.c:1537: error: ‘Z_FINISH’ undeclared (first use in this function)<br />
http_client.c:1540: error: ‘Z_BUF_ERROR’ undeclared (first use in this function)<br />
http_client.c:1540: error: ‘Z_STREAM_END’ undeclared (first use in this function)<br />
http_client.c: In function ‘destroy_unlink_conn’:<br />
http_client.c:1636: error: ‘struct conn_entry’ has no member named ‘q’<br />
.</code></p>
<p><code>.</code></p>
<p><code>. SNIP SNIP!</code></p>
<p><code>.</code></p>
<p><code><br />
http_client.c:2188: error: ‘struct conn_entry’ has no member named ‘next’<br />
http_client.c:2192: error: ‘struct conn_entry’ has no member named ‘q’<br />
In file included from database.c:33:<br />
http_client.h:26:25: error: openssl/ssl.h: No such file or directory<br />
In file included from database.c:33:<br />
http_client.h:189: error: expected specifier-qualifier-list before ‘SSL_CTX’<br />
In file included from crawler.c:30:<br />
http_client.h:26:25: error: openssl/ssl.h: No such file or directory<br />
In file included from crawler.c:30:<br />
http_client.h:189: error: expected specifier-qualifier-list before ‘SSL_CTX’<br />
In file included from analysis.c:28:<br />
http_client.h:26:25: error: openssl/ssl.h: No such file or directory<br />
In file included from analysis.c:28:<br />
http_client.h:189: error: expected specifier-qualifier-list before ‘SSL_CTX’<br />
analysis.c: In function ‘maybe_xsrf’:<br />
analysis.c:397: warning: implicit declaration of function ‘time’<br />
In file included from report.c:33:<br />
http_client.h:26:25: error: openssl/ssl.h: No such file or directory<br />
In file included from report.c:33:<br />
http_client.h:189: error: expected specifier-qualifier-list before ‘SSL_CTX’<br />
make: *** [skipfish] Error 1<br />
</code></p>
<p>Some digging about made me realise this is a fairly common problem even if your machine has a fairly good set of dependencies downloaded.</p>
<p>If you run the following command it should act as a catchall and set you up to be able to play with this tool.</p>
<p><code>sudo apt-get install libssl-dev build-essential zlibc zlib-bin libidn11-dev libidn11<br />
</code></p>
