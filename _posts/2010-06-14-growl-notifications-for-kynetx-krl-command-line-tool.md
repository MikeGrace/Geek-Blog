---
title: Growl Notifications for Kynetx KRL Command Line Tool
date: 2010-06-14T00:42:04+00:00
author: MikeGrace
layout: post
permalink: /2010/06/growl-notifications-for-kynetx-krl-command-line-tool/
categories:
  - How to
  - Kynetx
  - Linux
  - Mac OS
tags:
  - Bash
  - How to
  - Kynetx
  - Linux
  - Mac
  - Script
  - Terminal
  - Tools
---
<figure style="width: 396px" class="wp-caption aligncenter">[<img title="KRL Commit Growl Notification" src="https://mikegrace.s3.amazonaws.com/geek-blog/krl-commit-growl-notification.jpg" alt="KRL Commit Growl Notification" width="396" height="90" />](http://gist.github.com/437309)<figcaption class="wp-caption-text">KRL Commit Growl Notification</figcaption></figure> 

I have been using the [Kynetx KRL command line tool](http://github.com/kynetx/krl) for several weeks now and it has made my development of Kynetx apps much easier. The only problem that I have had as I have been using the command line tool is that once I commit my app I have to wait a few seconds before being able to run the new version in my browser. Until now I have been doing a lot of command + tab switching between windows to check to see if it has finished saving.

I have now created a clean solution that allows me to know when the version has finished being committed to the Kynetx servers and had one unexpected benefit.

I started out by creating a simple bash alias that would pipe the output from the &#8216;krl commit&#8217; command to a growl notification

<pre lang="bash"># Growl notify after krl commit is done
alias krlc="krl commit | growlnotify -t "KRL" --image /Users/mikegrace/src/kynetx-x.png;"</pre>

I quickly realized that this wouldn&#8217;t work for me because piping the console to the growl notification means that the commit output wouldn&#8217;t be visible on the console.  I need to be able to see on the console what the output was in case there were errors or the latest saved version so I started looking for a better solution and came up with [this](http://gist.github.com/437309)

<pre lang="bash"># Use growlnotify to alert user of commit status
krl() {
 if [[ $@ == "commit" ]]; then
  command krl commit | tee status.txt | growlnotify -t "KRL" --image /kynetx-x.png;
  cat status.txt;
 else
  command krl $@
 fi;
}</pre>

I created a function in my bash profile that runs when I run the krl command. When it sees me using the commit parameter it will do a krl commit and then tee that output to a status.txt file and pipe it to the growl notification. To have the output also show up on the console I cat the status.txt file back to the console. The unforeseen benefit here is that it is now really easy to share error output with others because it can be found in the status.txt file in the app folder.

I also created a bash script, [available on my github](http://gist.github.com/437280), that takes care of the installation for you. I created this script purely for fun and I had a blast doing it!

I had a really great time doing all of this and learned a lot. There is a lot of power in being able to manipulate command line tools to make tasks easier.

As Bigweld would say, &#8220;See a need, fill a need&#8221;