---
title: 'ErrorStack &#8211; Graphite &#8211; StatsD &#8211; NodeJS &#8211; Cron Success Story'
date: 2011-09-13T11:16:58+00:00
author: MikeGrace
layout: post
permalink: /2011/09/errorstack-graphite-statsd-nodejs-cron-success-story/
categories:
  - Other
---
At work I am implementing ErrorStack, Graphite, and StatsD into our projects and tools. We are doing this so we can better understand how our users interact with our products and so we can respond faster and more efficiently to errors.

  * [ErrorStack](http://errorstack.com/) helps us collect, report, and notify us of errors across all of our applications no matter where they are.
  * [Graphite](http://graphite.wikidot.com/) stores and graphes analytical data provided by our products.
  * [StatsD](https://github.com/etsy/statsd) run by [NodeJS](http://nodejs.org/) collects our analytical data via UDP so there is minimal impact on the performance of our applications as we collect the data.
  * [Cron](http://en.wikipedia.org/wiki/Cron) helps us run various tasks on our servers and helps us ensure that things are running smoothly

<div>
  I recently setup a Cron script to ensure that Node is running. If the script finds that Node is no longer running, it reports the issue to ErrorStack and then kicks off the process again. This ensures that we will be able to collect data via StatsD with minimal interruptions. Because I keep a browser window open to keep an eye on some key stats in graphite, I noticed a sudden drop in total metrics received and written to disk.
</div>

![](http://mikegrace.s3.amazonaws.com/geek-blog/drop-in-stats-graphite.jpg)

Just a minute or two later I got an email alert from ErrorStack notifying me that Node had died. After checking the graphite graph again I saw that the total metrics received had gone back up because the Cron script was able to restart the process. I love it when a plan comes together like that.

<pre lang="bash">#!/bin/bash
PID=`pidof node`
if [ $PID > 0 ]; then
  echo "node still running"
else
  echo "node died"
  curl -d "Msg=node died&_s=yourErrorStackKeyGoesHere&_r=json" http://www.errorstack.com/submit
  # command to start node server again goes here
fi</pre>

Here is some of the code that I use to report errors to ErrorStack <https://github.com/MikeGrace/ErrorStack-Reporting-Tools>