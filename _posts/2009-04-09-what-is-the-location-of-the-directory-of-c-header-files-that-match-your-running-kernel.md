---
title: What is the location of the directory of C header files that match your running kernel?
date: 2009-04-09T23:24:25+00:00
author: MikeGrace
layout: post
permalink: /2009/04/what-is-the-location-of-the-directory-of-c-header-files-that-match-your-running-kernel/
categories:
  - How to
  - Mac OS
tags:
  - Fedora
  - Linux
  - VMware
  - VMware Tools
---
<img src="/assets/2009/04/f10launch.png" alt="f10launch" title="f10launch" width="600" height="200" class="aligncenter size-full wp-image-76" srcset="/assets/2009/04/f10launch.png 600w, /assets/2009/04/f10launch-300x100.png 300w" sizes="(max-width: 600px) 100vw, 600px" />

# Installing VMware Tools for Fedora

### What Happened?

  * In VMware Fusion selected &#8220;Virtual Machine&#8221; &#8211;> &#8220;Install VMware Tools&#8221;
  * In a terminal navigate to folder with install file &#8220;/home/mike/Desktop/vmware-tools-distrib/&#8221;
  * Ran install with &#8220;./vmware-install.pl&#8221;
  * Accepted all default answers to prompts

### Problem

Was prompted with: 

#### What is the location of the directory of C header files that match your running
  
kernel? [/usr/src/linux/include]
  
</br></br>
  
The path &#8220;/usr/src/linux/include&#8221; is not an existing directory.

### Fix

  * Get kernal package name by entering &#8220;uname -r&#8221; into your terminal.
  * The returned string is what you need to search for in google. Might look like &#8220;2.6.27.21-170.2.56.fc10.i686&#8221;
  * Download the C header package found in your google search and install. I found mine at &#8220;http://rpmfind.net/linux/rpm2html/search.php?query=kernel-devel&#8221;
  * Installed C header files ended up in &#8220;/usr/src/kernels/[package name]/include/&#8221; for me. &#8220;[package name]&#8221; is the name of the package you downloaded and installed.

Hopefully doing that works for you as well as it did for me. Would love to hear if this helped and let me know if you have any questions.