---
title: Preventing console.log Undefined Errors
date: 2013-02-15T15:51:51+00:00
author: MikeGrace
layout: post
permalink: /2013/02/preventing-console-log-undefined-errors/
categories:
  - How to
  - JavaScript
  - Web Design -Dev
---
I don&#8217;t think it&#8217;s a good idea to leave 

<pre lang='javascript'>console.log</pre>

statements in production code, it&#8217;s a good idea to prevent your site from breaking if you accidentally do. I include this condition in the first script that loads on the page of most of my projects

<pre lang='javascript'>if (typeof console == "undefined") {
    window.console = {
        log: function () {}
    };
}
</pre>

This JavaScript simply defines an empty function if the console is not available in the browser so stray log statements don&#8217;t break production for your valuable customers.