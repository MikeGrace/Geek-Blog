---
title: WordPress Custom Post Type With Tags
date: 2014-04-24T22:54:39+00:00
author: MikeGrace
layout: post
permalink: /2014/04/wordpress-custom-post-type-with-tags/
categories:
  - How to
  - WordPress
tags:
  - How to
  - WordPress
---
I wanted to create a WordPress custom post type but have it be just like a regular blog post with all the same basic functionality. I was able to accomplish this by editing my theme&#8217;s functions and adding a hook into tho init event using the register\_post\_type function. Here is what it ended up looking like:

<pre lang="php">add_action( 'init', 'create_post_type' );
function create_post_type() {
    register_post_type( 'review',
        array(
            'labels' =&gt; array(
                'name' =&gt; __( 'Reviews' ),
                'singular_name' =&gt; __( 'Review' )
            ),
            'taxonomies' =&gt; array( 'post_tag' ),
            'public' =&gt; true,
            'has_archive' =&gt; true,
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

This is what the end result looks like. Just what I wanted.

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/wordpress-custom-post-type.jpg" alt="" width="400" height="431" />

&nbsp;

Resources

[https://codex.wordpress.org/Function\_Reference/register\_post_type](https://codex.wordpress.org/Function_Reference/register_post_type)

<https://codex.wordpress.org/Glossary#Post_Type>