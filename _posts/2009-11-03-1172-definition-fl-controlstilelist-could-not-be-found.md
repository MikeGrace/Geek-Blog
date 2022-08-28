---
title: '1172: Definition fl.controls:TileList could not be found.'
date: 2009-11-03T18:01:06+00:00
author: MikeGrace
layout: post
permalink: /2009/11/1172-definition-fl-controlstilelist-could-not-be-found/
categories:
  - ActionScript / Flash
  - How to
tags:
  - ActionScript
  - AS3
  - Flash
  - How to
---
[<img class="alignleft size-full wp-image-1007" title="Library" src="/assets/2009/11/3271730476_433a024f20_m.jpg" alt="Library" width="160" height="240" />](http://www.flickr.com/photos/eflon/3271730476/in/photostream/)I have been working on a flash project in ActionScript 3 lately for a class and I ran into an error. I have been trying to use a TileList component for a horizontally scrolling thumbnail gallery. The error was `1172: Definition fl.controls:TileList could not be found.` The beginning of my AS3 looked like:
  
`import fl.controls.TileList;<br />
import fl.controls.ScrollBarDirection;`
  
I tried dragging a TileList component from the Library and running it again and it worked! I deleted the TileList component from the stage and ran it again and it still worked. I&#8217;m not sure why I got these results but I am glad that my project is working again. Hope this helps some who might run into the same problem. If you know why this is the way it is I would love to know.

<div>
  Photo: <a rel="cc:attributionURL" href="http://www.flickr.com/photos/eflon/">http://www.flickr.com/photos/eflon/</a> / <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">CC BY 2.0</a>
</div>