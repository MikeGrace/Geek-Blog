---
title: Variable Length Excerpt for WordPress
date: 2014-04-25T17:06:59+00:00
author: MikeGrace
layout: post
permalink: /2014/04/variable-length-excerpt-for-wordpress/
categories:
  - How to
  - WordPress
tags:
  - How to
  - WordPress
---
If you need to change the default excerpt length you can do that through the use of the [excerpt_length filter](http://codex.wordpress.org/Plugin_API/Filter_Reference/excerpt_length).

If you need to be able to get varying length excerpts then you can add a custom function to your theme&#8217;s functions.php file like this:

<pre lang="php">// custom length excerpt as long as inside a loop
function custom_length_excerpt($word_count_limit) {
	echo wp_trim_words(get_the_content(), $word_count_limit);
}</pre>

Resources:
  
<http://stackoverflow.com/questions/4082662/multiple-excerpt-lengths-in-wordpress>
  
[http://codex.wordpress.org/Function\_Reference/wp\_trim_words](http://codex.wordpress.org/Function_Reference/wp_trim_words)
  
[http://codex.wordpress.org/Function\_Reference/get\_the_content](http://codex.wordpress.org/Function_Reference/get_the_content)