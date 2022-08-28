---
title: Xdebug Cachegrind and MAMP Pro on Mac OSX
date: 2011-08-10T13:31:18+00:00
author: MikeGrace
layout: post
permalink: /2011/08/xdebug-cachegrind-and-mamp-on-mac-osx/
categories:
  - How to
  - Web Design -Dev
---
Are you running MAMP on OSX? Want to profile your PHP code with Xdebug? It&#8217;s easy and here are the steps.

### How to run Xdebug on Mac OSX using MAMP

1 Start MAMP

2 Edit php.ini template file through MAMP to enable the extension. Edit the template file via File -> Edit Template -> PHP -> PHP [php version you are using] php.ini

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-edit-php-ini.jpg" alt="edit php.ini template for mamp on mac osx" width="650" height="120" />

3 Edit bottom of php.ini template file so that it ends up looking like if you want profile output

<pre lang="bash">[xdebug]
zend_extension="/Applications/MAMP/bin/php/php5.3.6/lib/php/extensions/no-debug-non-zts-20090626/xdebug.so"
xdebug.profiler_enable = 1
xdebug.profiler_output_dir = "/tmp"
; DONT REMOVE: MAMP PRO php5.3.6.ini template compatibility version: 1</pre>

If you don&#8217;t want profile output and just want xdebug running then use

<pre lang="bash">[xdebug]
zend_extension="/Applications/MAMP/bin/php/php5.3.6/lib/php/extensions/no-debug-non-zts-20090626/xdebug.so"
xdebug.profiler_enable = 0
xdebug.profiler_output_dir = "/tmp"
; DONT REMOVE: MAMP PRO php5.3.6.ini template compatibility version: 1</pre>

Now when you have errors, if they are sent to standard out, you will see something like this

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-error-view.jpg" alt="" width="611" height="379" />

My php.ini file:

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-php-ini-file.jpg" alt="edited php.ini file to run xdebug on mamp mac osx" width="650" height="420" />

4 Save edited template and close edit window

5 Restart MAMP

6 Open MAMP&#8217;s WebStart page and navigate to PHPInfo tab. Check to make sure that Xdebug is running. Doing a search in the browser window for &#8220;Xdebug&#8221; makes this easy.
  
<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-confirm-plugin-running.jpg" alt="confirm xdebug running on mamp on mac osx" width="650" height="317" />

7 If you used the same settings that I have above, when you run PHP code, Xdebug will put the cachegrind.out files in your &#8216;/tmp&#8217; directory. Open your &#8216;/temp&#8217; directory and run one of your PHP files to make sure it is working correctly. You can open the &#8216;/tmp&#8217; directory in finder by opening the terminal and running

<pre lang="bash">open /tmp</pre>

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-cachegrind-output-files.jpg" alt="cachegrind.out output in /temp folder for mamp on mac osx" width="650" height="295" />

8 Now you can use any app that understands those cachegrind.out files to view the profile data. Apps like [KCacheGrind](http://kcachegrind.sf.net/) (Linux/Windows, KDE), [WinCacheGrind](http://sourceforge.net/projects/wincachegrind) (Windows), [xdebugtoolkit](http://code.google.com/p/xdebugtoolkit/), and [Webgrind](http://code.google.com/p/webgrind/).  I went the simple route and used webgrind. Webgrind is a simple web based application that you can run locally on MAMP and it will look for the cachegrind.out files automatically with just one click. Continue for steps on setting up with webgrind.

9 [Download Webgrind](http://code.google.com/p/webgrind/downloads/list)

10 Setup Webgrind host on MAMP to run Webgrind

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-webgrind-host.jpg" alt="Setup webgrind as host on mamp to process xdebug php profile output" width="650" height="587" />

11 Visit webgrind url setup on your local MAMP installation. Mine was simply webgrind/

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-webgrind-installed.jpg" alt="" width="650" height="317" />

12 If you already have cachegrind output files you should be able to select the file in the &#8220;Auto (newest)&#8221; dropdown or leave it select at Auto and click update which will reveal the profile data

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-file-select.jpg" alt="" width="623" height="90" />

13 Throw a celebratory fist pump

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/xdebug-mamp-mac-osx-webgrind-success.jpg" alt="" width="650" height="360" />

&nbsp;

I think it&#8217;s awesome that the MAMP guys have included Xdebug with their [release of MAMP 2.01](http://forum.mamp.info/viewtopic.php?t=13799). I wrote this blog post because I wanted to be able to profile some of my projects to find areas where they could be improved. After finally figuring it out it was super simple. The problem was that it took me a long time to set up because of all of the incorrect and outdated information on the internet. I hope this makes it easier for others to get setup. If this post becomes outdated please leave a comment or contact me about what needs to be updated.

&#8212; UPDATE &#8212;

I am LOVING Xdebug! Just realized that when you do a var_dump of some variable, Xdebug formats it for you so it&#8217;s actually readable! AMAZING!!!!

Before:

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/php-var-dump-before-xdebug.png" alt="" width="480" height="352" />

After:

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/php-var-dump-after-xdebug.png" alt="" width="480" height="385" />

<span style="color: #888888;">Things I searched for to find my answers:</span>
  
<span style="color: #888888;">php profile</span>
  
<span style="color: #888888;">xdebug osx</span>
  
<span style="color: #888888;">mamp xdebug</span>
  
<span style="color: #888888;">php xdebug osx</span>
  
<span style="color: #888888;">webgrind</span>
  
<span style="color: #888888;">maccallgrind</span>
  
<span style="color: #888888;">cachegrind osx</span>
  
<span style="color: #888888;">cachegrind</span>
  
<span style="color: #888888;">valgrind</span>
  
<span style="color: #888888;">xdebug mamp</span>
  
<span style="color: #888888;">php.ini add extension mamp </span>