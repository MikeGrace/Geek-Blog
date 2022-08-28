---
title: JavaScript Simple Detect Touch Device
date: 2014-04-28T12:55:14+00:00
author: MikeGrace
layout: post
permalink: /2014/04/javascript-simple-detect-touch-device/
categories:
  - How to
  - JavaScript
  - Web Design -Dev
tags:
  - How to
  - web
---
Simple way to detect a touch device is by using a function like

`function isTouch() { return ('ontouchstart' in document.documentElement); }`