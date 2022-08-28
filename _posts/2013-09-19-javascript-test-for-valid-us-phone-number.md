---
title: JavaScript Test For Valid US Phone Number
date: 2013-09-19T08:50:05+00:00
author: MikeGrace
layout: post
permalink: /2013/09/javascript-test-for-valid-us-phone-number/
categories:
  - JavaScript
  - Web Design -Dev
---
TLDR;

Example and script at <http://sandbox.michaelgrace.org/phone-number-validation/>

In building an app, I needed to check for a valid phone number based on user input. After reading and learning more about US phone numbers than I cared about, I was able to come up with a basic way to check for a valid US phone number using JavaScript. It only marks a phone number as invalid if it is a phone number that is not a possible phone number or a special phone number that customers will not have (800 numbers, etc.).

[<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/random-photos/old-phone-in-booth.jpg" alt="" width="500" height="332" />](http://www.flickr.com/photos/ny156uk/433861528/)

I built a [US phone number validation test](http://sandbox.michaelgrace.org/phone-number-validation/) page that will test phone numbers you input and give the reason why it fails if it doesn&#8217;t pass validation. You can check it out at <http://sandbox.michaelgrace.org/phone-number-validation/>

Resources I ended up using in my research or the formulation of the algorithm:

  * [https://en.wikipedia.org/wiki/North\_American\_Numbering_Plan](https://en.wikipedia.org/wiki/North_American_Numbering_Plan)
  * <http://www.nanpa.com/area_codes/index.html>
  * [https://en.wikipedia.org/wiki/List\_of\_North\_American\_Numbering\_Plan\_area_codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)

&nbsp;

Photo by [Paul L](http://www.flickr.com/photos/ny156uk/433861528/)