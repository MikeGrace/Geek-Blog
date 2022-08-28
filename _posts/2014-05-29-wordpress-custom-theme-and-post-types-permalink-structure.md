---
title: WordPress Custom Theme and Post Types Permalink Structure
date: 2014-05-29T17:38:37+00:00
author: MikeGrace
layout: post
permalink: /2014/05/wordpress-custom-theme-and-post-types-permalink-structure/
categories:
  - How to
  - WordPress
---
I needed a way to have my theme blog posts all under /blog/ and all custom post types have their slug right off the root of the site.

/blog/
  
/blog/blog-post-title
  
/custom-post-type/
  
/other-custom-post-type/

By default, when I update the permalinks structure in the wp-admin to be /blog/%postname%/ all the custom post types got prepended with /blog/.

To fix this I updated the custom post type options when I register the post type in functions.php to:

<pre>'rewrite' =&gt; array( 'with_front' =&gt; false )</pre>

This fixed the issue and now all your permalinks are belong to us.

[Documentation: look for the **rewrite** section](http://codex.wordpress.org/Function_Reference/register_post_type)