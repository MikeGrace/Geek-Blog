---
title: Delete Data From Graphite
date: 2011-09-13T10:29:13+00:00
author: MikeGrace
layout: post
permalink: /2011/09/delete-data-from-graphite/
categories:
  - How to
  - Web Design -Dev
---
If you have set up a Graphite server and played with it like I have, you have some data in there cluttering up your interface. 

![graphite resource tree](http://mikegrace.s3.amazonaws.com/geek-blog/graphite-resource-tree.png)

You can get rid of any of the data or folders by deleting them from the server. The data is stored in files found starting at

<pre lang="bash">/opt/graphite/storage/whisper/</pre>

Happy deleting!