---
title: Set Production Flag in JavaScript Based on Domain Extension
date: 2013-02-15T15:42:31+00:00
author: MikeGrace
layout: post
permalink: /2013/02/set-production-flag-in-javascript-based-on-domain-extension/
categories:
  - How to
  - JavaScript
  - Web Design -Dev
---
In a recent project I wanted to be able to dynamically set a production flag in JavaScript. Doing so would allow me to keep my production analytics free from dev and staging environment events. Because my dev and staging environments don&#8217;t run on a .com domain extension I was able to go with this simple script

<pre lang='javascript'>var de = document.location.hostname.split('.');
    de = de[de.length - 1];
    window.prod = (de == 'com') ? true : false;
</pre>

Then when I need code to only respond when in production it&#8217;s as easy as

<pre lang='javascript'>if(window.prod) {
        // do awesomeness
    }
</pre>

Splitting up the domain in JavaScript to set the production flag has been working well and I&#8217;m quite happy with it so far. If you have suggestions or want to share what you have done, please share in the comments below.