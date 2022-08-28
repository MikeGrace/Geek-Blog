---
title: Accessing Template Variable From Snippet in MODX Revolution
date: 2013-02-19T09:39:56+00:00
author: MikeGrace
layout: post
permalink: /2013/02/accessing-template-variable-from-snippet-in-modx-revolution/
categories:
  - MODX
---
If you need to get the value of a template variable (TV) in [MODX](http://modx.com/) Revolution from within a snippet for the current resource, you can use
  
`$tvValue = $modx->resource->getTVValue('foo');`

More [MODX Revolution template variable documentation](http://rtfm.modx.com/display/revolution20/Accessing+Template+Variable+Values+via+the+API)