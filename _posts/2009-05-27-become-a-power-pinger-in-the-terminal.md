---
title: 'Become a power &#8220;pinger&#8221; in the Terminal'
date: 2009-05-27T00:32:06+00:00
author: MikeGrace
layout: post
permalink: /2009/05/become-a-power-pinger-in-the-terminal/
categories:
  - How to
  - Mac OS
tags:
  - Ping
  - Terminal
---
<p style="text-align: center;">
  <img class="aligncenter size-full wp-image-231" title="ping" src="/assets/2009/05/ping.jpg" alt="ping" width="600" height="445" srcset="/assets/2009/05/ping.jpg 600w, /assets/2009/05/ping-300x222.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" />
</p>

It is always fun to read the &#8220;man&#8221; pages in terminal and learn more about each command that I already use. I recently read the man page for ping and learned some cool stuff worthy of sharing.

**Ping in specific time intervals**

  * To ping at a time interval other than the default 1 second us the option flag of &#8216;-i [seconds to wait]&#8217;
  * Example: ping -i5 www.google.com 
      * This command will send a ping to google every 5 seconds
      * Note: It appears that any interval below 1 second requires root privileges

**Super Ping! aka &#8220;Flood ping&#8221;**
  
Personally, I think super ping sounds way cooler than flood ping but the later provides a better description of what it does.

  * According to the &#8220;man&#8221; pages, a flood will send out pings as fast as they come back or 100 pings/sec. Which ever one is happening faster will be the rule that is followed.
  * Example: sudo ping -f www.google.com 
      * This command will print a period to the console for every packet sent and will delete a period for every packet received. The cumulative effect of this is as more packets are dropped you will see more and more periods accumulate on the screen giving you instant feed back on how fast packets are being dropped.
      * Note: Use this command very wisely and with caution as it taxes your network.
      * With my internet connection, pinging google, I was able to send off 6,000 pings in 10 seconds.

The terminal is a very powerful tool!

[<img class="aligncenter size-full wp-image-225" title="archive_and_cite" src="/assets/2009/05/archive_and_cite.jpg" alt="archive_and_cite" width="300" height="188" />](http://www.webcitation.org/archive?url=http%3A//geek.michaelgrace.org/2009/05/become-a-power-pinger-in-the-terminal/&title=Become%20a%20power%20pinger%20in%20the%20Terminal&author=Mike%20Grace&date=2009-05-27&source=http%3A//geek.michaelgrace.org/&subject=terminal%3Bping%3Bunix%3Blinux)

Licensing
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;

You may remix, tweak, and build upon this work even for commercial reasons, as long as you credit me and license your new creations under these identical terms. All new works based on this work will carry the same license, so any derivatives will also allow commercial use. To credit this work please use the web citation and archive service found at [http://www.webcitation.org/archive](http://www.webcitation.org/archive?url=http%3A//geek.michaelgrace.org/2009/05/become-a-power-pinger-in-the-terminal/&title=Become%20a%20power%20pinger%20in%20the%20Terminal&author=Mike%20Grace&date=2009-05-27&source=http%3A//geek.michaelgrace.org/&subject=terminal%3Bping%3Bunix%3Blinux) or click on the &#8220;Archive & Cite this page!&#8221; image above.
  
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/us/"><img style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/us/88x31.png" alt="Creative Commons License" /></a>
  
<span>Become a power &#8220;pinger&#8221; in the Terminal</span> by <a rel="cc:attributionURL" href="http://geek.michaelgrace.org/">Mike Grace</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/us/">Creative Commons Attribution-Share Alike 3.0 United States License</a>.

Sources
  
&#8212;&#8212;&#8212;&#8212;&#8212;-
  
The &#8220;man&#8221; pages were used for the information found in this post. You can find the ping man page by typing into a unix or linux terminal the command &#8220;man ping&#8221; or a copy of several operating system man pages can be found at <http://manpages.unixforum.co.uk/>