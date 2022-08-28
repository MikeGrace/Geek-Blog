---
title: Running the Java Keytool on Mac
date: 2016-08-17T12:04:47+00:00
author: MikeGrace
layout: post
permalink: /2016/08/running-java-keytool-mac/
categories:
  - How to
  - Java
  - Mac OS
tags:
  - How to
  - Mac
---
Locate your java home directory by executing in Termal

<pre class="p1">/usr/libexec/java_home</pre>

This will return the full path to your java home directory on your Mac. Change into that directory and then you will be able to run the java keytool from there.

Here is a log of what I ran in Terminal on my Mac:

<pre class="p1"><span class="s1">$ /usr/libexec/java_home
</span><span class="s1">/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
</span><span class="s1">$ cd /System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home
$ keytool</span></pre>

<p class="p1">
  <a href="http://docs.oracle.com/javase/6/docs/technotes/tools/solaris/keytool.html"><span class="s1">keytool documentation</span></a>
</p>