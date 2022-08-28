---
title: 'Remove Duplicates From List &#8211; Quick and Easy'
date: 2016-11-21T13:00:19+00:00
author: MikeGrace
layout: post
permalink: /2016/11/remove-duplicates-list-quick-easy/
categories:
  - How to
tags:
  - How to
  - Python
---
I needed a quick way to take my several thousand plus list of numbers and remove all duplicates. Just a one off task where I didn&#8217;t care about the original order of the list, only that there should be no duplicates. Enter python! Here&#8217;s how I did it.

  1. Open Terminal on Mac
  2. Type &#8220;python&#8221; and execute
  3. Format my numbers in an array like [39213123667, 532092995671, 659203651894,&#8230; in a text editor for easy copy and paste
  4. Use python&#8217;s set to remove duplicates and then convert back to a list and print out:

<pre>listWithDuplicates = [39213123667, 532092995671, 659203651894,...

# sets are unordered collections of distinct objects
deduplicated = list(set(listWithDuplicates))

# used this to see how many duplicates were removed
len(listWithDuplicates)
len(deduplicated)

# print out list to start doing real work
deduplicated</pre>