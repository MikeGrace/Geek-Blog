---
title: JavaScript Performance Hit Calling Function vs. Inline
date: 2011-02-26T15:05:00+00:00
author: MikeGrace
layout: post
permalink: /2011/02/javascript-performance-hit-calling-function-vs-inline/
categories:
  - JavaScript
tags:
  - JavaScript
  - Performance
  - Testing
---
I know there is a performance hit when calling a function vs just running the code right there but I was curious how much that would be in different browsers. I went over to one of my favorite JS testing sites, <http://jsperf.com/> , and setup a simple test. Running a few tests on a few different browsers suggests that there is about a 50% performance hit when calling a function with a small task.

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/js-function-call-vs-inline-zoom.png" alt="" width="314" height="162" />

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/js-function-call-vs-inline.png" alt="" width="580" height="178" />

You can check out the most recent results at <http://jsperf.com/function-call-vs-inline> and test your own browser.