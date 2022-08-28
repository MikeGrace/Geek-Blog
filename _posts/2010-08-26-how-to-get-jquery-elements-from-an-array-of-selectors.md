---
title: How to get jQuery elements from an array of selectors
date: 2010-08-26T21:29:55+00:00
author: MikeGrace
layout: post
permalink: /2010/08/how-to-get-jquery-elements-from-an-array-of-selectors/
categories:
  - How to
  - Web Design -Dev
tags:
  - How to
  - JavaScript
  - jQuery
  - web
---
[<img alt="" src="https://mikegrace.s3.amazonaws.com/geek-blog/buckets.jpg" class="alignnone" width="240" height="160" />](http://www.flickr.com/photos/lanchongzi/3421470726/)
  
<del datetime="2010-08-27T04:17:45+00:00">To use an array of strings as jQuery selectors I have found the need to append an empty string.</del>
  
My bad example works because it coerces the &#8216;this&#8217; object to a string.

Bad Example:

<pre lang="javascript">array = ["h1","p","div"];
$K(array).each(function() {
    console.warn( $K(this+"").children() );
});
</pre>

Much Better Example:

<pre lang="javascript">array = ["h1","p","div"];
$K(array).each(function(index, value) {
    console.warn( $K(value).children() );
});
</pre>

I had previously tried the following with out success

<pre lang="javascript">array = ["h1","p","div"];
$K(array).each(function() {
    console.warn( $K(this).children() );
});
</pre>

<del datetime="2010-08-27T04:17:45+00:00">The problem of what I was originally trying was that each item in the array wasn&#8217;t being treated as a string, I think.</del>The problem of what I was originally trying was that &#8216;this&#8217; is an object and not a string like I need for the jQuery selector. 

A big thanks goes out to my friends,[Alex Olson](https://twitter.com/alexkolson) & [Sam Curren](http://twitter.com/telegramsam), for helping me understand my mistake while being tired. 

If I didn&#8217;t need to do something different for each time through the loop I could do something like this [stack overflow answer:](http://stackoverflow.com/questions/1002073/an-array-of-strings-as-a-jquery-selector)

<pre lang="javascript">array = ["h1","p","div"];
console.warn( $K( array.join(", ") ).children() );
</pre>