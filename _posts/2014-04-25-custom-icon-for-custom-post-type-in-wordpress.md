---
title: Custom Icon for Custom Post Type in WordPress
date: 2014-04-25T17:50:34+00:00
author: MikeGrace
layout: post
permalink: /2014/04/custom-icon-for-custom-post-type-in-wordpress/
categories:
  - How to
  - WordPress
tags:
  - How to
  - WordPress
---
<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/dashicons.png" alt="" width="500" height="311" />

If you have created a [custom post type in WordPress](http://geek.michaelgrace.org/2014/04/wordpress-custom-post-type-with-tags/) then you should customize the icon for your custom post type. As of version 3.8 it&#8217;s a easy as adding another parameter to your post type.

  1. Visit <http://melchoyce.github.io/dashicons/>
  2. Pick desired icon and get name of icon
  3. Add name of dashicon to menu\_icon parameter in register\_post_type options array

<pre lang="php">'menu_icon' =&gt; 'dashicons-megaphone'</pre>

In context it looks like this:

<pre lang="php">add_action( 'init', 'create_post_type' );
function create_post_type() {
  register_post_type( 'experience',
    array(
      'labels' =&gt; array(
        'name' =&gt; __( 'Experiences' ),
        'singular_name' =&gt; __( 'Experience' )
      ),
      'taxonomies' =&gt; array( 'category' ),
      'public' =&gt; true,
      'has_archive' =&gt; true,
      'menu_icon' =&gt; 'dashicons-megaphone',
      'supports' =&gt; array(
        'title',
        'editor',
        'author',
        'thumbnail',
        'custom-fields',
        'comments',
        'revisions'
      )
    )
  );
}</pre>