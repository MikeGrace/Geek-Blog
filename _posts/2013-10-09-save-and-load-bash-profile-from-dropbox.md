---
title: Save And Load Bash Profile From Dropbox
date: 2013-10-09T07:44:55+00:00
author: MikeGrace
layout: post
permalink: /2013/10/save-and-load-bash-profile-from-dropbox/
categories:
  - How to
  - Linux
  - Mac OS
tags:
  - How to
  - Mac
  - Terminal
---
With using different machines and installing a fresh copy of the latest Mac OS every year, I am constantly loosing my .profile. The .profile is a file used to save settings, shortcuts, and more awesomeness for your command line use in the Terminal app on Mac OS. I wanted to save my profile file to dropbox so I could use the same one across multiple machines and have it backed up. Here is how I did it.

  1. Move or create your profile file in Dropbox where you want it. I put mine at <span style="color: #993300;">~/Dropbox/Apps/Terminal/profile.txt</span>.
  2. Make sure you don&#8217;t have a .profile file in your home folder so we can create a soft link to the dropbox version.
  3. Open Terminal and run the command to create a soft link to the dropbox version of the .profile. Your command may be different but will probably look something like

<pre><span style="color: #993300;">ln -s ~/Dropbox/Apps/Terminal/profile.txt ~/.profile</span></pre>

&nbsp;

Now when you open a new terminal window, so the new profile is loaded, you will be using the profile from Dropbox instead of your home folder. Now in your home directory if you list out your files, you should see the soft link for the .profile pointing to the Dropbox version. Here is what mine looks like:

<img class="alignnone" alt="bash profile linked to dropbox location" src="http://mikegrace.s3.amazonaws.com/geek-blog/Terminal/link-bash-profile-to-dropbox-location.jpg" width="650" height="158" />