---
title: Where Are the Default Mac OS X Icons
date: 2009-10-03T21:28:36+00:00
author: MikeGrace
layout: post
permalink: /2009/10/where-are-the-default-mac-os-x-icons/
categories:
  - How to
  - Mac OS
tags:
  - Apple
  - How to
  - OS
  - Terminal
---
<img class="size-full wp-image-965 alignleft" title="FinderIcon" src="/assets/2009/10/FinderIcon.png" alt="FinderIcon" width="128" height="128" />
  
**Question:**
  
Where are the default Mac OS X Icons in .icns format?

**Answer:**

<pre lang="bash">/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources</pre>

<img class="alignleft size-full wp-image-972" title="ErasingIcon" src="/assets/2009/10/ErasingIcon.png" alt="ErasingIcon" width="128" height="128" />

**How to get there:**

you can get there several different ways.
  
**1)** Paste into Terminal

<pre lang="bash">cd /System/Library/CoreServices/CoreTypes.bundle/Contents/Resources; open .</pre>

**2)** Open Finder -> Select &#8220;Go&#8221; menu item -> Select &#8220;Go to Folder&#8221; -> Paste

<pre lang="bash">/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources</pre>

**3)** Open Finder -> (Keyboard Shortcut) Shift + Command + G -> Paste

<pre lang="bash">/System/Library/CoreServices/CoreTypes.bundle/Contents/Resources</pre>