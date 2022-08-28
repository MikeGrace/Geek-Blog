---
title: 'Colon In XML/RSS Messing Up PHP&#8217;s SimpleXML'
date: 2011-10-17T10:06:56+00:00
author: MikeGrace
layout: post
permalink: /2011/10/colon-in-xmlrss-messing-up-phps-simplexml/
categories:
  - How to
  - Web Design -Dev
tags:
  - bug
  - php
  - simplexml
---
Recently used PHP&#8217;s simpleXML to parse through a blogs RSS feed. The parsing worked great and it was simple and clean. Only problem was that the XML nodes that contained colons in the name were being discarded by simpleXML. Example:

<pre lang="xml">&lt;sy:updatePeriod>hourly&lt;/sy:updatePeriod>
&lt;sy:updateFrequency>1&lt;/sy:updateFrequency></pre>

Not sure if this is a bug, error, or what but it was causing me grief. I haven&#8217;t been able to find others on the web complaining of this but my own solution was to remove the colons and traverse accordingly. I wrote a function that takes the feed as a string and returns the string with all colons inside tag names removed.

<pre lang="php">function removeColonsFromRSS($feed) {
    // pull out colons from start tags
    // (&lt;\w+):(\w+>)
    $pattern = '/(&lt;\w+):(\w+>)/i';
    $replacement = '$1$2';
    $feed = preg_replace($pattern, $replacement, $feed);
    // pull out colons from end tags
    // (&lt;\/\w+):(\w+>)
    $pattern = '/(&lt;\/\w+):(\w+>)/i';
    $replacement = '$1$2';
    $feed = preg_replace($pattern, $replacement, $feed);
    return $feed;
}</pre>