---
title: 'Jira Filter &#8211; See my watched issues not assigned to me'
date: 2016-09-07T12:29:55+00:00
author: MikeGrace
layout: post
permalink: /2016/09/jira-filter-see-watched-issues-not-assigned/
categories:
  - How to
tags:
  - How to
---
To see issues in Jira that I am watching but are not assigned to me I created a new filter

<pre>issue in watchedIssues() AND assignee not in (currentUser())</pre>

Go to the filters view, select advanced, paste in the jql provided.

<img class="size-large wp-image-2542 alignnone" src="/assets/2016/09/Screen-Shot-2016-09-07-at-11.28.41-AM.jpg" alt="screen-shot-2016-09-07-at-11-28-41-am" width="600" height="90" srcset="/assets/2016/09/Screen-Shot-2016-09-07-at-11.28.41-AM.jpg 600w, /assets/2016/09/Screen-Shot-2016-09-07-at-11.28.41-AM-300x45.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" />

<img class="size-full wp-image-2541 alignnone" src="/assets/2016/09/Screen-Shot-2016-09-07-at-11.28.22-AM.jpg" alt="screen-shot-2016-09-07-at-11-28-22-am" width="600" height="175" srcset="/assets/2016/09/Screen-Shot-2016-09-07-at-11.28.22-AM.jpg 600w, /assets/2016/09/Screen-Shot-2016-09-07-at-11.28.22-AM-300x88.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" />

If you want to get fancy you could add another condition to show unresolved tickets like

<pre>issue in watchedIssues() AND assignee not in (currentUser()) AND resolution = Unresolved</pre>