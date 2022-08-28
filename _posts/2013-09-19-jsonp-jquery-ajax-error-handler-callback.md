---
title: JSONP jQuery Ajax Error Handler Callback
date: 2013-09-19T08:30:16+00:00
author: MikeGrace
layout: post
permalink: /2013/09/jsonp-jquery-ajax-error-handler-callback/
categories:
  - How to
  - Web Design -Dev
tags:
  - Browser
  - How to
  - JavaScript
---
Are you using JSONP and jQuery and trying to handle non 200 responses? Getting frustrated that your error handler isn&#8217;t firing when it gets a 403, 404, or some other response code? Take a breath and repeat after me.

### &#8220;There is no error handling in JSONP&#8221;

Now that you have fallen into a great despair, let me save you.

Head over to <https://github.com/jaubourg/jquery-jsonp> to find a good alternative to jQuery&#8217;s implementation of JSONP.

The solution was easy to implement and helped me solve the issues I was having with getting 403 and 404 errors on JSONP requests.

jQuery-JSONP is feature rich with

  * _error recovery_ in case of network failure or ill-formed JSON responses,
  * precise _control over callback naming_ and how it is transmitted in the URL,
  * multiple requests with the _same callback name running concurrently_,
  * _two caching mechanisms_ (browser-based and page based),
  * the possibility to _manually abort_ the request just like any other AJAX request,
  * a _timeout_ mechanism.

and compatible with all major browsers

  * _Internet Explorer 6+_
  * _Firefox 2+_
  * _Chrome 1+_
  * _Safari 3+_
  * _Opera 9+_

<img class="alignnone" alt="" src="http://mikegrace.s3.amazonaws.com/geek-blog/random-photos/shattered-rock.jpg" width="500" height="331" />

Photo by [janet galore](http://www.flickr.com/photos/janetgalore/4511491128/)