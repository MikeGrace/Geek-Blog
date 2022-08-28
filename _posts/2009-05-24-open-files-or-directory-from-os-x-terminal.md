---
title: open files or directory from OS X terminal
date: 2009-05-24T15:20:36+00:00
author: MikeGrace
layout: post
permalink: /2009/05/open-files-or-directory-from-os-x-terminal/
categories:
  - How to
  - Mac OS
tags:
  - Bash
  - Finder
  - How to
  - Mac OS X
  - Terminal
---
<figure id="attachment_170" style="width: 500px" class="wp-caption aligncenter"><img src="/assets/2009/05/terminal_finder_love.jpg" alt="Terminal loves Finder" title="terminal_finder_love" width="500" height="218" class="size-full wp-image-170" srcset="/assets/2009/05/terminal_finder_love.jpg 500w, /assets/2009/05/terminal_finder_love-300x130.jpg 300w" sizes="(max-width: 500px) 100vw, 500px" /><figcaption class="wp-caption-text">Terminal loves Finder</figcaption></figure> 

In Mac OS X Terminal open the current folder in Finder by using the command &#8216;open .&#8217; You can also open a file with its default application by using &#8216;open fileName.fileExtension&#8217;

Examples:

If the current working directory in terminal is &#8220;/System/Library&#8221; then &#8216;open .&#8217; would open &#8220;/System/Library&#8221; in finder.

&#8216;open test.txt&#8217; would open the text file &#8220;test.txt&#8221; in TextEdit.

&#8216;open *&#8217; would open all the files in the current directory with their default applications.

&#8216;open *.jpg&#8217; opens all jpg images in folder.

&#8216;open [ABC]*.pdf&#8217; opens all pdfs that start with an uppercase A, B, or C.

The possibilities and the power of the &#8216;open&#8217; command in terminal are astounding. Learn even more about the command by using the command &#8216;man open&#8217; or just &#8216;open&#8217; and the terminal will display more information on that command and how it is used. If you use the &#8216;man open&#8217; command spacebar will show the next page and &#8216;q&#8217; will exit the **man**ual.

Sources
  
&#8212;&#8212;&#8212;&#8212;-
  
The heart in the image was acquired from <http://www.eyehook.com/free/love.html> under the [Creative Commons Attribution 2.5 Generic License](http://creativecommons.org/licenses/by/2.5/)

URL: <http://www.eyehook.com/free/love.html> Accessed: 2009-4-24. (Archived by WebCite&reg; at <http://www.webcitation.org/5h1DQldAm>)

**License**
  
&#8212;&#8212;&#8212;&#8212;-
  
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/us/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/us/88x31.png" /></a>  
<span xmlns:dc="http://purl.org/dc/elements/1.1/" property="dc:title">Open files or directory in Finder from OS X Terminal</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="http://geek.michaelgrace.org/" property="cc:attributionName" rel="cc:attributionURL">Mike Grace</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/us/">Creative Commons Attribution-Share Alike 3.0 United States License</a>.