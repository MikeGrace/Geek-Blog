---
title: Uploading Browser Extensions To S3 Using Transmit
date: 2011-02-21T17:33:42+00:00
author: MikeGrace
layout: post
permalink: /2011/02/uploading-browser-extensions-to-s3-using-transmit/
categories:
  - Chrome
  - Firefox
  - How to
tags:
  - S3
  - Transmit
---
I create a lot of browser extensions and like to upload them to S3. It&#8217;s super nice to have each respective browser automatically start the install process on download. To do this, specific headers need to be set on the file and it&#8217;s SUPER easy with Transmit.

1) Open Transmit preferences

2) View &#8220;Cloud&#8221; options

3) Add custom header for crx file extensions (content-type text/plain)
  
<img alt="" src="http://mikegrace.s3.amazonaws.com/geek-blog/transmit-s3-chrome-extension.png" class="alignnone" width="600" height="374" />

4) Add custom header for xpi file extensions (content-type application/x-xpinstall)
  
<img alt="" src="http://mikegrace.s3.amazonaws.com/geek-blog/transmit-s3-firefox-extension.png" class="alignnone" width="600" height="374" />

Once these are set, every time a file with one of those extensions gets uploaded the proper headers will be set and your user&#8217;s browsers will automatically start the install process.