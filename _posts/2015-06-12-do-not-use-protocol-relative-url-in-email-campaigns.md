---
title: Do Not Use Protocol Relative URL in Email Campaigns
date: 2015-06-12T16:37:29+00:00
author: MikeGrace
layout: post
permalink: /2015/06/do-not-use-protocol-relative-url-in-email-campaigns/
audio_file:
  - ""
duration:
  - ""
filesize:
  - ""
date_recorded:
  - ""
explicit:
  - ""
block:
  - ""
pe_theme_Mentor:
  - 'O:8:"stdClass":6:{s:7:"sidebar";O:8:"stdClass":1:{s:5:"value";s:7:"default";}s:6:"footer";O:8:"stdClass":1:{s:5:"value";s:6:"footer";}s:7:"gallery";O:8:"stdClass":5:{s:2:"id";s:3:"114";s:4:"type";s:10:"thumbnails";s:5:"title";s:7:"gallery";s:6:"custom";s:0:"";s:5:"delay";s:1:"0";}s:5:"image";O:8:"stdClass":1:{s:5:"scale";s:4:"fill";}s:5:"video";O:8:"stdClass":1:{s:2:"id";s:2:"-1";}s:5:"quote";O:8:"stdClass":2:{s:4:"text";s:117:""Lorem ipsum dolor sit amet, <a href="#">consectetuer adipiscing elit</a>, donec odio. Quisque volutpat mattis eros."";s:4:"sign";s:18:"John Dough, Client";}}'
categories:
  - Tech
tags:
  - How to
  - tech
---
The [Protocol relative URL](https://en.wikipedia.org/wiki/Wikipedia:Protocol-relative_URL) is awesome! If you do use these types of links, be sure to NOT use them in your email campaigns. Depending on the email client that is being used, the link will be broken. Protocol relative links received in Mac Mail app will turn

//www.yourwebsite.com/promotion-link/

into

x-webdoc://www.yourwebsite.com/promotion-link/

If you can use either http or https you really should be using and forcing https. It makes the web a better place and can help prevent things like [GitHub&#8217;s man on the side attack](http://www.netresec.com/?page=Blog&month=2015-03&post=China%27s-Man-on-the-Side-Attack-on-GitHub) happening to you.

[Chain photo by pratanti (CC BY 2.0)](https://www.flickr.com/photos/pratanti/5359581911/in/photolist-9aBfYF-3ghYNw-8XUCEy-Mzwxn-9PUWMA-9mYQX8-k19iJo-cUz5GY-pXFm2m-edKSt4-or6wKf-edRxyb-r4a1WD-krWgUv-fSg3j-iw6ee2-qNjqYH-edRxw3-2mZc5E-8H9mxb-atFCvY-c4fwwW-25BYRZ-7xasj7-GqVeV-azHUYV-7vkgwu-7Q4pLF-oCBKux-bQL9SX-czHgYY-89EoTN-p8UVRb-82hdoX-druWBL-4S2mbg-tJNKZK-qWLUp6-6YzmM-7Bj6bf-qePnFA-4M1RJT-obH3wM-e3RrX8-6k6h4Y-7hEsyx-6Q1TF3-jP2Adr-nAk8Rp-2GChy)