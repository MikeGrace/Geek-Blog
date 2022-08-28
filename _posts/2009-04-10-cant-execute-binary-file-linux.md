---
title: 'Can&#8217;t execute binary file &#8211; linux'
date: 2009-04-10T00:07:22+00:00
author: MikeGrace
layout: post
permalink: /2009/04/cant-execute-binary-file-linux/
categories:
  - How to
tags:
  - Bash
  - chmod
  - execute
  - file permission
  - Linux
  - Terminal
---
### <img class="aligncenter size-full wp-image-83" title="terminal" src="/assets/2009/04/terminal.jpg" alt="terminal" width="391" height="219" srcset="/assets/2009/04/terminal.jpg 391w, /assets/2009/04/terminal-300x168.jpg 300w" sizes="(max-width: 391px) 100vw, 391px" />

### The Problem

Executing binary file in terminal fails returning &#8220;Can&#8217;t execute binary file&#8221;.

### Fix

In terminal enter &#8220;chmod +x [filename]&#8221;

### Why

chmod +x adds the permission for the user to execute the binary file.

&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
References

chmod. Wikipedia. URL:<http://en.wikipedia.org/wiki/Chmod>. Accessed: 2009-04-10. (Archived by WebCite® at <http://www.webcitation.org/5fvIhQ3Zg>)