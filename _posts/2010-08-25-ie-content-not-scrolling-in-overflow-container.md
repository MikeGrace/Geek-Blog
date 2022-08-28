---
title: IE content not scrolling in overflow container
date: 2010-08-25T02:53:05+00:00
author: MikeGrace
layout: post
permalink: /2010/08/ie-content-not-scrolling-in-overflow-container/
categories:
  - Web Design -Dev
tags:
  - Browser
  - How to
  - IE
  - web
---
<figure style="width: 184px" class="wp-caption alignnone">[<img title="IE content not scrolling bug" src="https://mikegrace.s3.amazonaws.com/geek-blog/scroll-bug.jpg" alt="IE content not scrolling bug" width="184" height="240" />](http://www.flickr.com/photos/ektogamat/3097557335/)<figcaption class="wp-caption-text">IE content not scrolling bug</figcaption></figure> 

If you have some content in a container and the content isn&#8217;t scrolling, there is probably an easy fix. If any of the content inside the container that is position relative, the container must also be position relative.

Doesn&#8217;t work in IE

<pre lang="html4strict"><div id="scroller" style="overflow-y:scroll">
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
  
</div></pre>

Works in IE

<pre lang="html4strict"><div id="scroller" style="overflow-y:scroll;position:relative">
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
    
  
  <p style="position:relative">
    Lorem ipsum dolor sit amet, consectetur
  </p>
  
</div></pre>

Photo by [Anderson Mancini](http://www.flickr.com/photos/ektogamat/3097557335/)