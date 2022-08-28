---
title: ie error expected identifier string or number
date: 2010-08-24T23:20:55+00:00
author: MikeGrace
layout: post
permalink: /2010/08/ie-error-expected-identifier-string-or-number/
categories:
  - How to
  - Web Design -Dev
tags:
  - Error
  - How to
  - IE
  - JavaScript
  - web
---
<figure style="width: 174px" class="wp-caption alignnone">[<img title="ie error expected identifier string or number" src="https://mikegrace.s3.amazonaws.com/geek-blog/comma.jpg" alt="ie error expected identifier string or number" width="174" height="240" />](http://www.flickr.com/photos/stealingsand/4543877957/)<figcaption class="wp-caption-text">ie error expected identifier string or number</figcaption></figure> 

IE 7 was throwing an error while working on some JavaScript

> ie error expected identifier string or number

The problem was that I had an extra comma in a hash

<pre lang="javascript">this.css({
      "position":"fixed",
      "top": ( $K(window).height() - this.height() ) / 2 + "px",
      "left": ( $K(window).width() - this.width() ) / 2 + "px",
    });</pre>

It should have been

<pre lang="javascript">this.css({
      "position":"fixed",
      "top": ( $K(window).height() - this.height() ) / 2 + "px",
      "left": ( $K(window).width() - this.width() ) / 2 + "px"
    });</pre>

Photo: By [stealingsand](http://www.flickr.com/photos/stealingsand/4543877957/)