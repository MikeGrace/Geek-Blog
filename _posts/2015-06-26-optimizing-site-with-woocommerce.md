---
title: Optimizing Site with WooCommerce
date: 2015-06-26T16:28:58+00:00
author: MikeGrace
layout: post
permalink: /2015/06/optimizing-site-with-woocommerce/
pe_theme_Mentor:
  - 'O:8:"stdClass":6:{s:7:"sidebar";O:8:"stdClass":1:{s:5:"value";s:7:"default";}s:6:"footer";O:8:"stdClass":1:{s:5:"value";s:6:"footer";}s:7:"gallery";O:8:"stdClass":5:{s:2:"id";s:3:"114";s:4:"type";s:10:"thumbnails";s:5:"title";s:7:"gallery";s:6:"custom";s:0:"";s:5:"delay";s:1:"0";}s:5:"image";O:8:"stdClass":1:{s:5:"scale";s:4:"fill";}s:5:"video";O:8:"stdClass":1:{s:2:"id";s:2:"-1";}s:5:"quote";O:8:"stdClass":2:{s:4:"text";s:117:""Lorem ipsum dolor sit amet, <a href="#">consectetuer adipiscing elit</a>, donec odio. Quisque volutpat mattis eros."";s:4:"sign";s:18:"John Dough, Client";}}'
block:
  - ""
explicit:
  - ""
date_recorded:
  - ""
filesize:
  - ""
duration:
  - ""
audio_file:
  - ""
categories:
  - Tech
tags:
  - tech
  - WordPress
---
If you are optimizing a site with WooCommerce, you might find that WooCommerce adds a lot of scripts and styles to every single page of your site. Most likely, this is unnecessary and can be optimized to improve page load times and page weights.

For a full explanation and background on the issue, check out <https://wordimpress.com/how-to-load-woocommerce-scripts-and-styles-only-in-shop/> where Devin Walker breaks it all down. For posterity sake, here is the [snippet of code that goes in the functions.php file](https://gist.github.com/MikeGrace/201431761fa93902a7e4) of WordPress:

&nbsp;

<pre>/**
 * Optimize WooCommerce Scripts
 * Remove WooCommerce Generator tag, styles, and scripts from non WooCommerce pages.
 */
add_action( 'wp_enqueue_scripts', 'child_manage_woocommerce_styles', 99 );

function child_manage_woocommerce_styles() {
	//remove generator meta tag
	remove_action( 'wp_head', array( $GLOBALS['woocommerce'], 'generator' ) );

	//first check that woo exists to prevent fatal errors
	if ( function_exists( 'is_woocommerce' ) ) {
		//dequeue scripts and styles
		if ( ! is_woocommerce() && ! is_cart() && ! is_checkout() ) {
			wp_dequeue_style( 'woocommerce_frontend_styles' );
			wp_dequeue_style( 'woocommerce_fancybox_styles' );
			wp_dequeue_style( 'woocommerce_chosen_styles' );
			wp_dequeue_style( 'woocommerce_prettyPhoto_css' );
			wp_dequeue_script( 'wc_price_slider' );
			wp_dequeue_script( 'wc-single-product' );
			wp_dequeue_script( 'wc-add-to-cart' );
			wp_dequeue_script( 'wc-cart-fragments' );
			wp_dequeue_script( 'wc-checkout' );
			wp_dequeue_script( 'wc-add-to-cart-variation' );
			wp_dequeue_script( 'wc-single-product' );
			wp_dequeue_script( 'wc-cart' );
			wp_dequeue_script( 'wc-chosen' );
			wp_dequeue_script( 'woocommerce' );
			wp_dequeue_script( 'prettyPhoto' );
			wp_dequeue_script( 'prettyPhoto-init' );
			wp_dequeue_script( 'jquery-blockui' );
			wp_dequeue_script( 'jquery-placeholder' );
			wp_dequeue_script( 'fancybox' );
			wp_dequeue_script( 'jqueryui' );
		}
	}

}</pre>