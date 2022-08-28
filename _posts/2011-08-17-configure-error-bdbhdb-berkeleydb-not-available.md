---
title: 'configure: error: BDB/HDB: BerkeleyDB not available'
date: 2011-08-17T14:12:50+00:00
author: MikeGrace
layout: post
permalink: /2011/08/configure-error-bdbhdb-berkeleydb-not-available/
categories:
  - Linux
---
If you get the error

> configure: error: BDB/HDB: BerkeleyDB not available

Make sure you have BerkleyDB installed by running something like

<pre lang="bash">sudo yum install db4</pre>

You may also have to run

<pre lang="bash">sudo yum install db4-devel</pre>