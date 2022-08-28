---
title: Advanced Google Chrome Logging
date: 2012-08-28T00:28:45+00:00
author: MikeGrace
layout: post
permalink: /2012/08/advanced-google-chrome-logging/
categories:
  - Chrome
  - How to
  - Web Design -Dev
tags:
  - logging
---
tldr;

Run in terminal:

`/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --enable-logging --v=1&<br />
tail -f ~/Library/Application\ Support/Google/Chrome/chrome_debug.log`

If you are wondering how to know just about everything that Google Chrome is doing, you can enable verbose logging to a file. If you are running on a Mac, you can follow similar steps to launch Google Chrome in verbose logging mode.

  * Make sure Google Chrome is not already running
  * Open Terminal
  * Find path to Google Chrome that most closely resembles the following

`/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome`

  * Once verified, launch Google chrome with verbose logging flag by running verified path with flags

`/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --enable-logging --v=1`

  * Find logging file, chrome_debug.log, that most likely lives at

`~/Library/Application\ Support/Google/Chrome`

  * Watch the file for updates using tail or some other application

`tail -f ~/Library/Application\ Support/Google/Chrome/chrome_debug.log`

This is using Google Chrome version 21<figure style="width: 394px" class="wp-caption alignnone">

<img title="Google Chrome Logging" src="http://mikegrace.s3.amazonaws.com/geek-blog/google-chrome-advanced-logging.jpg" alt="Google Chrome Logging" width="394" height="245" /><figcaption class="wp-caption-text">Google Chrome Logging</figcaption></figure> 

&nbsp;<figure style="width: 500px" class="wp-caption alignnone">

<img title="Google Chrome logging to Terminal" src="http://mikegrace.s3.amazonaws.com/geek-blog/google-chrome-logging-terminal.jpg" alt="Google Chrome logging to Terminal" width="500" height="326" /><figcaption class="wp-caption-text">Google Chrome logging to Terminal</figcaption></figure> 

Web Resources:

<http://www.chromium.org/for-testers/enable-logging>
  
<http://peter.sh/experiments/chromium-command-line-switches/>
  
<http://superuser.com/q/157484/2861>