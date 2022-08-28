---
title: Getting into jQuery
date: 2010-07-21T08:11:45+00:00
author: MikeGrace
layout: post
permalink: /2010/07/getting-into-jquery/
categories:
  - Education
  - How to
  - Web Design -Dev
tags:
  - jQuery
---
<p style="text-align: center;">
  <a title="Swiss Army Knife Cadet 1 by Quality &amp; Style, on Flickr" href="http://www.flickr.com/photos/qualityandstyle/4567136254/"><img src="http://farm5.static.flickr.com/4038/4567136254_9c64cd1f54.jpg" alt="Swiss Army Knife Cadet 1" width="500" height="287" /></a>
</p>

<div style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: #ffffff; font: normal normal normal 13px/19px Georgia, 'Times New Roman', 'Bitstream Charter', Times, serif; font-family: Times; line-height: normal; font-size: small; padding: 0.6em; margin: 0px;">
  <p>
    I have a friend that is wanting to get into learning and using jQuery so I thought that I would throw some information together to help them get started.
  </p>
  
  <h2 style="font-size: 1.5em;">
    Documentation
  </h2>
  
  <p>
    Love jQuery&#8217;s documentation! I love being able to go to <a href="http://api.jquery.com/">http://api.jquery.com/</a> and being able to quickly search for what I am looking for. This is great for when I know roughly what I want and just need a bit of information on how to do it. When I was starting out, the documentation main page was the place to be <a href="http://docs.jquery.com/">http://docs.jquery.com/</a>
  </p>
  
  <h2 style="font-size: 1.5em;">
    Including jQuery into projects
  </h2>
  
  <p>
    So you can download the jQuery code from the site and put it up on S3 or your own hosting service and include it into your projects that you are working on but why not let Google do it for you if it makes life easier? Google has a bunch of script libraries that they host for free that are used commonly. To include jQuery in your project stress free try this<br /> <img src="https://mikegrace.s3.amazonaws.com/geek-blog/jquery-example-1/google-jquery.png" alt="" width="660" height="24" />
  </p>
  
  <h2 style="font-size: 1.5em;">
    Document Ready
  </h2>
  
  <p>
    One thing that can be frustrating when just starting out using jQuery is finding out the hard way of why you have to wait for the page to load before your functions can work. What??!! jQuery is a JavaScript library that extends native functionality of JavaScript and just plain makes JavaScript easier to work with. Problem is, none of your jQuery functions will work until the library is completely loaded and the structure of the html is in the browser. You can make sure your jQuery functions don&#8217;t try to do anything until the page is ready by putting your code in a document read wrapper that jQuery makes easy.
  </p>
  
  <pre style="font: normal normal normal 12px/18px Consolas, Monaco, 'Courier New', Courier, monospace;" lang="html">$(document).ready(function() {
  // Your jQuery code goes here
});</pre>
  
  <h2 style="font-size: 1.5em;">
  </h2>
  
  <h2 style="font-size: 1.5em;">
    Shortcut
  </h2>
  
  <p>
    Because using jQuery is soo awesome and you are going to be using it soo much, the shortcut &#8216;$&#8217; was used to reference jQuery. So the following two jQuery functions are the same.
  </p>
  
  <pre style="font: normal normal normal 12px/18px Consolas, Monaco, 'Courier New', Courier, monospace;" lang="html">jQuery("#ajax img").hide();
$("#ajax img").hide();</pre>
  
  <h2 style="font-size: 1.5em;">
  </h2>
  
  <h2 style="font-size: 1.5em;">
    Help
  </h2>
  
  <p>
    Just remember when you get frustrated or you need help understanding something with jQuery do a Google search for what your having trouble with. If that doesn&#8217;t get you what you are looking for, ask a friend! There are many who have loved using jQuery and would love to help a friend out. Also, don&#8217;t forget the ever awesome <a href="http://stackoverflow.com/ ">http://stackoverflow.com/ </a>which is a great place to find, ask, and answer programming related stuff! jQuery included.
  </p>
  
  <h2>
    Example
  </h2>
  
  <p>
    Here is a full and simple working example that I created just to show off a bit of the fun power of jQuery. Again, jQuery documentation rocks and has many examples but I thought this would be nice to pull together everything I had talked about here.
  </p>
  
  <p>
    <a href="https://mikegrace.s3.amazonaws.com/geek-blog/jquery-example-1/jquery-example-1.html">https://mikegrace.s3.amazonaws.com/geek-blog/jquery-example-1/jquery-example-1.html</a>
  </p>
  
  <p>
    photo by <a href="http://www.flickr.com/photos/qualityandstyle/4567136254/">Quality & Style</a></div>