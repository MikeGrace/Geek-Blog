---
title: 'IE8 &#038; IE7 JavaScript Date NaN From String Error'
date: 2013-09-11T07:21:15+00:00
author: MikeGrace
layout: post
permalink: /2013/09/ie8-ie7-javascript-date-nan-from-string-error/
categories:
  - How to
  - JavaScript
tags:
  - Browser
  - How to
  - IE
  - JavaScript
---
When trying to create a JavaScript Date object from a string I was getting an NaN error in IE7 and IE8. My JavaScript worked in all the other browsers I was testing in. I was writing the script to figure out future dates based on the date the user selected. Issue is that IE7 and 8 don&#8217;t handle strings as well as real browsers. I was able to fix the error by using date.setFullYear instead of expecting the browser to handle it. Found a great function in [StackOverflow.com](http://stackoverflow.com/a/2182529/117068) to handle this.

&nbsp;

<pre lang="javascript">function parseISO8601(dateStringInRange) {
	var isoExp = /^\s*(\d{4})-(\d\d)-(\d\d)\s*$/,
		date = new Date(NaN), month,
		parts = isoExp.exec(dateStringInRange);

	if(parts) {
		month = +parts[2];
		date.setFullYear(parts[1], month - 1, parts[3]);
		if(month != date.getMonth() + 1) {
			date.setTime(NaN);
		}
	}
	return date;
}</pre>

You can check out my [reduced test case](http://mikegrace.s3.amazonaws.com/geek-blog/ie-date-object-from-string-error/test.html).