---
title: Double Key Press Activation State Machine Thingy!
date: 2011-02-26T19:09:13+00:00
author: MikeGrace
layout: post
permalink: /2011/02/double-key-press-activation-state-machine-thingy/
categories:
  - How to
  - JavaScript
tags:
  - JavaScript
  - Keyboard
  - State-Machine
---
I&#8217;m working on building a documentation search tool based on QuickSilver and Alfred App. I needed a way to activate the search so I built this demo in preparation for finishing the search tool. You can check out the live demo at

<http://mikegrace.s3.amazonaws.com/geek-blog/double-tap/double-tap.html>

This is what it looks like even though the code is the fun part:

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/double-tap/double-tap-example-screenshot.png" alt="" width="483" height="482" />

The demo code will shift states as you press the &#8216;s&#8217; key. If you press the &#8216;s&#8217; key quickly enough back to back it will switch to the activated state and stay there until the &#8216;esc&#8217; key is pressed causing it to reset. The code also won&#8217;t change state if the focus is in a textarea or input to prevent activation while a user is typing in an area they don&#8217;t want to be interrupted in. I will have to add an exception for the search tool input box when I implement this to allow the &#8216;esc&#8217; key to reset and hide the search tool while inside of it. You can use the code if you like and I would love to hear any feedback that anyone has about it.

###### Tested on Mac 10.6.6 with Firefox 3.6, Chrome 9.0, Safari 5.0, and Opera 11.01