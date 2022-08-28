---
title: How to use JavaScript setTimeout function
date: 2010-10-20T11:22:07+00:00
author: MikeGrace
layout: post
permalink: /2010/10/how-to-use-javascript-settimeout-function/
categories:
  - How to
  - Web Design -Dev
---
If you are wanting to run some JavaScript once after a set time, you should use setTimeout.

<pre lang="javascript">setTimeout(function() {
    // JavaScript code executes here
}, 3000)
</pre>

The first parameter of the setTimeout is the JavaScript function that will be executed once the delay is up. The second parameter is the amount of time to delay in milliseconds. 

It is possible to pass the setTimeout function a string in the first parameter as the JavaScript to execute but this is a bad idea. Passing the JavaScript as a string means that it must go through eval() to be executed. eval() == evil. It&#8217;s also difficult to pass parameters to a function when using strings that must go through eval(). Passing an anonymous function instead of a string is also easier to read for developers.