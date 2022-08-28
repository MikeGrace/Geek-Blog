---
title: IE8 IE7 403 HTTPS/SSL Error MAMP Fix
date: 2013-09-11T06:28:04+00:00
author: MikeGrace
layout: post
permalink: /2013/09/ie8-ie7-403-httpsssl-error-mamp-fix/
categories:
  - How to
tags:
  - Browser
  - How to
  - IE
  - MAMP
---
I was using [browserstack.com](http://www.browserstack.com/) to test a website on my local machine using [MAMP](http://www.mamp.info) when everything looked fine except on IE8 and IE7. I was getting 403 forbidden errors when trying to load the site in IE7 and 8 on Windows XP. Apparently the default SSL apache configuration in MAMP is set to not accept connections from browsers that don&#8217;t support [Server Name Indication](http://wiki.apache.org/httpd/NameBasedSSLVHostsWithSNI). &#8220;SNI&#8221; is supported on Internet Explorer 7.0 or later (on Vista, not XP). The solution is to comment out a line in the apache configuration that rejects requests from non SNI compatible browsers.

## MAMP Solution

1. Open Apache httpd-ssl.conf template file for editing

<img class="alignnone" alt="edit apache httpd-ssl.conf file in mamp template" src="http://mikegrace.s3.amazonaws.com/geek-blog/ie-ssl-403-error/open-mamp-apache-httpd-ssl.conf-template.jpg" width="500" height="252" />

2. Comment out line

<pre>SSLStrictSNIVHostCheck on</pre>

to be

<pre>#SSLStrictSNIVHostCheck on</pre>

<img class="alignnone" alt="httpd-ssl.conf line to comment out" src="http://mikegrace.s3.amazonaws.com/geek-blog/ie-ssl-403-error/mamp-httpd-ssl.conf-line-to-edit.jpg" width="500" height="433" />

3. Restart MAMP to have Apache reload httpd-ssl.conf

<img class="alignnone" alt="restart mamp server" src="http://mikegrace.s3.amazonaws.com/geek-blog/ie-ssl-403-error/restart-mamp-server.jpg" width="500" height="454" />

&nbsp;

Hope this how-to helped save you some of the frustration I had.