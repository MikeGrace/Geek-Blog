---
title: Laravel, Debugbar, and LiveReload
date: 2014-09-08T17:47:45+00:00
author: MikeGrace
layout: post
permalink: /2014/09/laravel-debugbar-and-livereload/
categories:
  - How to
---
Ran into a gotcha today while using [Debugbar](https://github.com/barryvdh/laravel-debugbar) with Laravel and LiveReload. For every request, Debugbar creates a json file in the app storage with information on the request. This is great except it was triggering the browser extension to reload the page because there was a file change in the app.

To fix add the debugbar storage folder to the exclusion list. 1) Select monitored folders 2) Select options 3) Add folder to exclusion list 4) Save

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/live-reload-debugbar-folder.jpg" alt="" width="800" height="590" />

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/live-reload-debugbar.jpg" alt="" width="800" height="590" />