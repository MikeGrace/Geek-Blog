---
title: Create HTML link That Starts A Skype Call
date: 2010-03-06T14:35:58+00:00
author: MikeGrace
layout: post
permalink: /2010/03/create-html-link-that-starts-a-skype-call/
categories:
  - How to
  - Web Design -Dev
tags:
  - How to
  - skype
---
Update &#8211; 2012.01.15

You can get officially generated skype buttons for your web page at <a href="http://www.skype.com/intl/en-us/tell-a-friend/get-a-skype-button/" target="_blank">http://www.skype.com/intl/en-us/tell-a-friend/get-a-skype-button/</a> which offers a button that shows your current status!

* * *

<img class="aligncenter" src="https://mikegrace.s3.amazonaws.com/geek-blog/skpe-me.png" alt="" width="600" height="108" />
  
To create a link that visitors can click on to call a phone number or skype username follow this syntax.
  
_Replace the asterisks with a valid username or number._

## Phone Number:

<pre lang="html4strict"><a href="callto://+***********">Link will initiate Skype to call my number!</a></pre>

## Skype Username:

<pre lang="html4strict"><a href="skype:********?call">Link will initiate Skype to call my Skype username!</a></pre>