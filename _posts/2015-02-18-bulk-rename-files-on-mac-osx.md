---
title: Bulk Rename Files on Mac OSX
date: 2015-02-18T21:44:57+00:00
author: MikeGrace
layout: post
permalink: /2015/02/bulk-rename-files-on-mac-osx/
categories:
  - How to
  - Linux
  - Mac OS
---
With the need to rename lots of files in bulk I have come to love a terminal application called &#8216;rename&#8217;. On Mac you can install it using Brew by running

brew install rename

Then if you want to rename all the files in a directory so they have a hyphen instead of an underscore you just do

rename -n &#8216;s/_/-/&#8217; *

The -n flag says to run it as a test and don&#8217;t actually change the files. Once I confirm that it is working, I run it again without the test flag like so

rename -v &#8216;s/_/-/&#8217; *

The v flag outputs what files were changed. You can find a few more examples at <http://tips.webdesign10.com/how-to-bulk-rename-files-in-linux-in-the-terminal>