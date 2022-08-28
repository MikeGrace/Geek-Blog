---
title: Webkit Rendering Bug When Animating Absolutely Positioned Elements
date: 2012-10-10T11:54:47+00:00
author: MikeGrace
layout: post
permalink: /2012/10/webkit-rendering-bug-when-animating-absolutely-positioned-elements/
categories:
  - Web Design -Dev
---
## ADD A Z-INDEX TO YOUR ABSOLUTELY POSITIONED ELEMENTS!

While building a web app, I ran into an issue with Chrome and Safari having a strange rendering issue when animating absolutely positioned elements. In testing it worked fine in IE and Firefox so I thought I was going crazy.

Come to find out, if I added a z-index to the absolutely positioned elements that I was animating the issue went away. I was able to figure out the issue after finding this StackOverflow.com answer at

<http://stackoverflow.com/questions/10522054/weird-rendering-bug-in-desktop-webkit-safari-chrome-with-absolutely-positioned>

after doing a google search for &#8220;webkit animate absolutely positioned elements rendering bug&#8221;