---
title: Checking Keyframe misalignment between video renditions
date: 2016-07-08T11:18:17+00:00
author: MikeGrace
layout: post
permalink: /2016/07/checking-keyframe-misalignment-video-renditions/
categories:
  - Video
tags:
  - How to
  - keyframe
  - stuttering
  - Tools
  - video
---
Keyframe misalignment can cause stuttering when switching between renditions. To check for this you can use a tool like [aegisub](http://www.aegisub.org/).

Load each video
  
<img class="size-full wp-image-2525 alignnone" src="/assets/2016/07/Screen-Shot-2016-07-08-at-10.10.28-AM.jpg" alt="Screen Shot 2016-07-08 at 10.10.28 AM" width="400" height="144" srcset="/assets/2016/07/Screen-Shot-2016-07-08-at-10.10.28-AM.jpg 400w, /assets/2016/07/Screen-Shot-2016-07-08-at-10.10.28-AM-300x108.jpg 300w" sizes="(max-width: 400px) 100vw, 400px" />

Export keyframe text file
  
<img class="size-full wp-image-2526 alignnone" src="/assets/2016/07/Screen-Shot-2016-07-08-at-10.10.50-AM.jpg" alt="Screen Shot 2016-07-08 at 10.10.50 AM" width="400" height="392" srcset="/assets/2016/07/Screen-Shot-2016-07-08-at-10.10.50-AM.jpg 400w, /assets/2016/07/Screen-Shot-2016-07-08-at-10.10.50-AM-300x294.jpg 300w" sizes="(max-width: 400px) 100vw, 400px" />

Compare the files for differences. If the keyframes are aligned, the keyframe text files should all be identical.