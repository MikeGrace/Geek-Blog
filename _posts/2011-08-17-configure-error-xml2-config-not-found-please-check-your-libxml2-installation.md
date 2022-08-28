---
title: 'configure: error: xml2-config not found. Please check your libxml2 installation.'
date: 2011-08-17T13:45:33+00:00
author: MikeGrace
layout: post
permalink: /2011/08/configure-error-xml2-config-not-found-please-check-your-libxml2-installation/
categories:
  - Linux
---
If you get the error

> configure: error: xml2-config not found. Please check your libxml2 installation.

try installing libxml2-devel by running something like

<pre lang="bash">sudo yum install libxml2-devel</pre>