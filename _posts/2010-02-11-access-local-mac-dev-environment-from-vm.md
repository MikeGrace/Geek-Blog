---
title: Access Local Mac Dev Environment from VM
date: 2010-02-11T14:20:04+00:00
author: MikeGrace
layout: post
permalink: /2010/02/access-local-mac-dev-environment-from-vm/
categories:
  - How to
  - Mac OS
  - Web Design -Dev
tags:
  - Browser
  - Database
  - Development
  - How to
  - IE
  - Linux
  - Mac
  - Safari
  - Testing
  - Tools
  - Virtual-Machine
  - VM
---
Testing my web development in IE is the bane of my existence. Since I run Apache and MYSQL on my local host on my Mac it was always a trick to view my work though my Windows VM until my friend [Mike Farmer](http://twitter.com/mikefarmer) showed me an easy way to access my development environment on my Mac from my virtual machine.

Steps:

  1. Get default gateway of VM machine
  2. Use that address the same way you would &#8220;localhost&#8221; on your Mac

Example:<figure style="width: 538px" class="wp-caption alignnone">

<img title="Get IP address of VM" src="https://geek-blog.s3.amazonaws.com/2010/xp-cmd-ipaddress.jpg" alt="Get IP address of VM" width="538" height="351" /><figcaption class="wp-caption-text">Get IP address of VM</figcaption></figure> <figure style="width: 600px" class="wp-caption alignnone"><img class=" " title="Local Mac development environment" src="https://geek-blog.s3.amazonaws.com/2010/mac-local-couchdb-environment.jpg" alt="Local Mac development environment" width="600" height="441" /><figcaption class="wp-caption-text">Local Mac development environment</figcaption></figure> <figure style="width: 600px" class="wp-caption alignnone"><img class=" " title="Dev environment from VM" src="https://mikegrace.s3.amazonaws.com/geek-blog/xp-access-mac-dev-environment.jpg" alt="Dev environment from VM" width="600" height="441" /><figcaption class="wp-caption-text">Dev environment from VM</figcaption></figure>