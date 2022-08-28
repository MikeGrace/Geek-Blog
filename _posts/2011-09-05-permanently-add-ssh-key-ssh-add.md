---
title: Permanently Add SSH key ssh-add
date: 2011-09-05T14:19:05+00:00
author: MikeGrace
layout: post
permalink: /2011/09/permanently-add-ssh-key-ssh-add/
categories:
  - How to
  - Mac OS
---
Recently on my Mac I wanted to add a second SSH key to my authentication agent. Using the ssh-add command I was able to do just that until I restarted my computer. To add the key each time I start up a new terminal session I just added

<pre lang="bash">ssh-add ~/.ssh/ec2.pem > /dev/null 2>&1</pre>

to my .profile file located at ~/.profile

The last part of the command is to route the output of the command to dev null so I don&#8217;t see it when I open up terminal.

<pre lang="bash">> /dev/null 2>&1</pre>