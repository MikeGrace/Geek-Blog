---
title: Tracing PHP Memory Usage using Xdebug and Mamp on Mac
date: 2012-04-18T09:44:28+00:00
author: MikeGrace
layout: post
permalink: /2012/04/tracing-php-memory-usage-using-xdebug-and-mamp-on-mac/
categories:
  - How to
  - Mac OS
  - Web Design -Dev
tags:
  - How to
  - Mac
  - MAMP
  - php
  - Tools
  - Xdebug
---
I recently wanted to see which parts of my app were using the most memory in a PHP script. I&#8217;ve been using Xdebug and webgrind on MAMP on my local machine and loving it. Derick Rethans wrote a post a few years ago about <a href="http://derickrethans.nl/xdebug-and-tracing-memory-usage.html" target="_blank">how to use Xdebug to profile memory usage</a> and it was fairly easy to get it working.

1. [Setup Xdebug](http://geek.michaelgrace.org/2011/08/xdebug-cachegrind-and-mamp-on-mac-osx/) on your Mac on MAMP.

2. Set Xdebug to output the needed function traces by adding the following to the php5.3.6.ini file:

<pre lang='bash'>xdebug.show_mem_delta = 1
xdebug.trace_format = 1
xdebug.trace_enable_trigger = 1
xdebug.auto_trace = 1
xdebug.trace_output_dir = "/tmp"
</pre>

How to edit php .ini file in MAMP:
  
![](http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-edit-php-ini.jpg)

In context screenshot:
  
![](http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-memory-settings.png)

3. Restart MAMP
  
![](http://mikegrace.s3.amazonaws.com/geek-blog/mamp-restart.png)

4. <a href="https://github.com/derickr/xdebug/raw/master/contrib/tracefile-analyser.php" target="_blank">Download Derick&#8217;s parsing script</a> to parse out memory usage from .xt trace files. I downloaded the script to my home directory to keep it simple.

5. Run PHP script that you want to measure memory usage from and confirm that .xt trace file is output to the /tmp directory. My output file was named

<pre lang='bash'>/tmp/trace.2043925204.xt
</pre>

6. Run Derick&#8217;s memory parsing script against output .xt file

<pre lang='bash'>~/memory.php /tmp/trace.2043925204.xt memory-own 20
</pre>

Example output:

<pre lang='bash'>parsing...

Done.

Showing the 20 most costly calls sorted by 'memory-own'.

                                 Inclusive        Own
function                 #calls  time     memory  time     memory
-----------------------------------------------------------------
{main}                        1  0.0345  2303008  0.0085  1894608
EpiRoute->addRoute          107  0.0058    97344  0.0034    92208
EpiApi->addRoute             61  0.0014    49304  0.0014    49304
EpiRoute->get                64  0.0050    65280  0.0017     6608
include_once                  8  0.0003     6376  0.0002     6120
Epi::getSetting             108  0.0024     5184  0.0024     5184
dbConnection                  2  0.0007     4760  0.0001     4568
EpiApi->get                  33  0.0062    63112  0.0014     4224
EpiRoute->post               43  0.0037    42736  0.0012     4064
EpiApi->post                 28  0.0058    54088  0.0013     3584
getApi                       61  0.0011     3344  0.0011     3344
mysqli->prepare               2  0.0003     2640  0.0003     2640
require                       4  0.0003     2312  0.0002     2312
session_start                 1  0.0001     2216  0.0001     2216
include                       5  0.0006     3192  0.0003      880
fsockopen                     2  0.0015      880  0.0015      880
func_get_args                 2  0.0000      840  0.0000      840
EpiTemplate->display          1  0.0008     4288  0.0002      776
EpiRoute::getInstance       108  0.0022      528  0.0022      528
EpiRoute->getRoute            1  0.0002      728  0.0001      480
</pre>