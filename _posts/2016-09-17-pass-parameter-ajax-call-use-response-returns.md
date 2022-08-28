---
title: Pass parameter to Ajax call to use after response returns
date: 2016-09-17T01:25:59+00:00
author: MikeGrace
layout: post
permalink: /2016/09/pass-parameter-ajax-call-use-response-returns/
categories:
  - How to
  - JavaScript
tags:
  - JavaScript
  - jQuery
---
Let&#8217;s say I have some data I want to pass along with an ajax call to use when the response comes in. You can pass round trip parameters in your jQuery ajax call by adding them to the options object like this
  
`</p>
<pre>$.ajax({
 url: 'www.example.com/some-api/',
 dataType: "json",
 roundTripVariable: 'Weeeeee!',
 success: function(data, textStatus, jqXHR) {
 // will print 'Weeeeee!' to the console
 console.log( this.roundTripVariable );
 }
});</pre>
<p>`