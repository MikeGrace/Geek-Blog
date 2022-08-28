---
title: Rhino and Envjs
date: 2011-09-06T14:56:11+00:00
author: MikeGrace
layout: post
permalink: /2011/09/rhino-and-envjs/
categories:
  - How to
  - JavaScript
  - Web Design -Dev
---
[Rhino](http://www.mozilla.org/rhino/) is an open source implementation of JavaScript in Java and [envjs](http://www.envjs.com/) is a simulated browser environment written in javascript. So what does all this mean? It means that you can load up a web page and execute the loaded page&#8217;s JavaScript in a browser simulated environment all without a browser! Let me demonstrate.

From the [Rhino downloads page](https://developer.mozilla.org/en/Rhino_downloads_archive) I downloaded [rhino1_7R2.zip](ftp://ftp.mozilla.org/pub/mozilla.org/js/rhino1_7R2.zip) since <span style="text-decoration: underline;"><strong>R3 doesn&#8217;t work with Envjs at the time of this post.</strong></span>

I also downloaded the latest [Envjs](http://www.envjs.com/) and placed it in the same location as the unzipped rhino folder.

Navigate in a terminal to the location of the unziped rhino folder and start up rhino.

<pre lang="bash">java -jar js.jar</pre>

Then you will want to load the Envjs JavaScript that will emulate the browser environment. (location is relative to where the jar file is running from)

<pre lang="bash">load("../env.rhino.js")</pre>

Then I tell Envjs to load external scripts found in the page. This is required because scripts running in Rhino with Envjs will have file system access.

<pre lang="javascript">Envjs.scriptTypes['text/javascript'] = true;</pre>

Then we navigate our emulated browser to the test page that I built.

<pre lang="javascript">window.location = "http://mikegrace.s3.amazonaws.com/geek-blog/rhino-envjs.html"</pre>

The test page that I built looks like this when you load it in a browser with JavaScript disabled

![](http://mikegrace.s3.amazonaws.com/geek-blog/rhino-envjs-test-page-js-disabled.png)

This is because the page content is built using jQuery

<pre lang="html4strict">Rhino and Envjs Test</pre>

Because Envjs will emulate a browser, we will be able to work with the page in Rhino like we would in a browser.

![](http://mikegrace.s3.amazonaws.com/geek-blog/rhino-envjs-test-page-js-enabled.png)

Getting the paragraph text is as easy as running some jQuery in the Rhino console

<pre lang="javascript">jQuery("p").text();</pre>

Awesome!

<pre lang="bash">rhino1_7R2 mgrace$ java -jar js.jar
Rhino 1.7 release 2 2009 03 22
js&gt; load("../env.rhino.js")
[  Envjs/1.6 (Rhino; U; Mac OS X x86_64 10.6.8; en-US; rv:1.7.0.rc2) Resig/20070309 PilotFish/1.2.13  ]
js&gt; Envjs.scriptTypes['text/javascript'] = true;
true
js&gt; window.location = "http://mikegrace.s3.amazonaws.com/geek-blog/rhino-envjs.html"
http://mikegrace.s3.amazonaws.com/geek-blog/rhino-envjs.html
js&gt; jQuery("p").text();
Question: What is the answer?
js&gt; jQuery("code").text();
42</pre>

![](http://mikegrace.s3.amazonaws.com/geek-blog/running-rhino-envjs-from-console.png)

If you are looking to debug your scripts in Rhino a bit better, you can launch the rhino console in the Rhino JavaScript Debugger using a command similar to this

<pre lang="bash">java -cp js.jar org.mozilla.javascript.tools.debugger.Main</pre>

![rhino javascript debugger](http://mikegrace.s3.amazonaws.com/geek-blog/rhino-javascript-debugger.png)