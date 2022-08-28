---
title: Standup Meeting Kynetx App
date: 2011-01-13T16:30:04+00:00
author: MikeGrace
layout: post
permalink: /2011/01/standup-meeting-kynetx-app/
categories:
  - Kynetx
tags:
  - Browser
  - Kynetx
  - Tools
  - web
---
I&#8217;m really glad I had some time to build another Kynetx app that the Kynetx team will be able to use to be more efficient with their time. [I had the idea a few days ago](http://mikegrace.tumblr.com/post/2685369401/recent-kynetx-app-ideas-and-thoughts) and now that idea is a reality. Here is what I explained my idea to be on my other blog

> At work we have standup meetings each morning to discuss roadblocks and the plan for the day. Often, most of the time is spent relating what is going to be done for the day which isn’t working very well. I want to build an app that each employee would install that would remind them each morning to submit their short list of what they are working on for the day and would show what everyone else is working on for the day. A user could dismiss the promptings for the day on all sites and could see the list anytime by going to a predefined url where the days tasks and road blocks would be listed. This app would probably use a Google spreadsheet to facilitate this functionality because it would be nice to have this information recorded even though it could be done through app variables.

Demo video:



Here are some action shots showing how the app works:

Installing the browser extension and loading a page for the first time. The time happens to be between 6 am and 10 am. You&#8217;ll notice that the app runs on whatever url you are currently on. It doesn&#8217;t look so great if it happens to be a site that has a lot of crazy stuff going on like Google reader or flash sites.

[<img class="alignnone size-medium wp-image-1596" title="Screen shot 2011-01-13 at 12.02.58 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.02.58-PM-300x280.png" alt="Screen shot 2011-01-13 at 12.02.58 PM" width="300" height="280" srcset="/assets/2011/01/Screen-shot-2011-01-13-at-12.02.58-PM-300x280.png 300w, /assets/2011/01/Screen-shot-2011-01-13-at-12.02.58-PM.png 962w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.02.58-PM.png)

Once the user submits the day&#8217;s standup items the app confirms submission and removes itself from the page

[<img class="alignnone size-medium wp-image-1599" title="Screen shot 2011-01-13 at 12.03.19 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.19-PM-300x199.png" alt="Screen shot 2011-01-13 at 12.03.19 PM" width="300" height="199" srcset="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.19-PM-300x199.png 300w, /assets/2011/01/Screen-shot-2011-01-13-at-12.03.19-PM.png 437w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.03.19-PM.png)

On all pages that the user visits between the hours of 6 am and 10 am a little icon will be annotated in the bottom right corner of the browser window.

[<img class="alignnone size-medium wp-image-1600" title="Screen shot 2011-01-13 at 12.03.24 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.24-PM-300x280.png" alt="Screen shot 2011-01-13 at 12.03.24 PM" width="300" height="280" srcset="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.24-PM-300x280.png 300w, /assets/2011/01/Screen-shot-2011-01-13-at-12.03.24-PM.png 962w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.03.24-PM.png)

[<img class="alignnone size-full wp-image-1601" title="Screen shot 2011-01-13 at 12.03.24 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.24-PM1.png" alt="Screen shot 2011-01-13 at 12.03.24 PM" width="199" height="175" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.03.24-PM1.png)

When a user hovers over the annotation, it will reveal two action buttons. The list button will show a list of everyone&#8217;s submitted standup items for the day. The x button will removed the annotation from the page if it is in the way.

[<img class="alignnone size-full wp-image-1602" title="Screen shot 2011-01-13 at 12.03.35 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.35-PM.png" alt="Screen shot 2011-01-13 at 12.03.35 PM" width="131" height="141" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.03.35-PM.png)

When a user clicks on the list button, the standup items will be listed in a notify and the annotation will remove itself from the current page.

[<img class="alignnone size-medium wp-image-1603" title="Screen shot 2011-01-13 at 12.03.42 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.42-PM-300x223.png" alt="Screen shot 2011-01-13 at 12.03.42 PM" width="300" height="223" srcset="/assets/2011/01/Screen-shot-2011-01-13-at-12.03.42-PM-300x223.png 300w, /assets/2011/01/Screen-shot-2011-01-13-at-12.03.42-PM.png 413w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.03.42-PM.png)

After the first time a user has used the app, it will remember the user&#8217;s name so the user doesn&#8217;t have to enter it again.

[<img class="alignnone size-full wp-image-1604" title="Screen shot 2011-01-13 at 12.04.41 PM" src="/assets/2011/01/Screen-shot-2011-01-13-at-12.04.41-PM.png" alt="Screen shot 2011-01-13 at 12.04.41 PM" width="383" height="376" srcset="/assets/2011/01/Screen-shot-2011-01-13-at-12.04.41-PM.png 383w, /assets/2011/01/Screen-shot-2011-01-13-at-12.04.41-PM-300x294.png 300w" sizes="(max-width: 383px) 100vw, 383px" />](/assets/2011/01/Screen-shot-2011-01-13-at-12.04.41-PM.png)

I won&#8217;t be sharing the extensions I built for the Kynetx team but I plan on sharing the code along with explinations on www.kynetxappaday.wordpress.com soon. Hope this app has gotten you thinking about ways you could use something similar or maybe completely different apps you could build using Kynetx.

<h2 style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: transparent; vertical-align: baseline; clear: both; font-weight: normal; background-position: initial initial; background-repeat: initial initial; padding: 0px; margin: 0px; border: 0px initial initial;">
  Questions?
</h2>

<a style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: transparent; vertical-align: baseline; color: #0066cc; text-decoration: none; background-position: initial initial; background-repeat: initial initial; padding: 0px; margin: 0px; border: 0px initial initial;" href="http://docs.kynetx.com/">KRL Documentation</a>
  
<a style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: transparent; vertical-align: baseline; color: #0066cc; text-decoration: none; background-position: initial initial; background-repeat: initial initial; padding: 0px; margin: 0px; border: 0px initial initial;" href="http://stackoverflow.com/questions/ask?tags=KRL">Ask KRL question on StackOverflow.com</a>
  
<a style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: transparent; vertical-align: baseline; color: #0066cc; text-decoration: none; background-position: initial initial; background-repeat: initial initial; padding: 0px; margin: 0px; border: 0px initial initial;" href="http://twitter.com/MikeGrace">Ask @MikeGrace on Twitter</a>
  
<a style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: transparent; vertical-align: baseline; color: #0066cc; text-decoration: none; background-position: initial initial; background-repeat: initial initial; padding: 0px; margin: 0px; border: 0px initial initial;" href="http://twitter.com/Kynetx">Ask @Kynetx on Twitter</a>
  
<a style="background-image: initial; background-attachment: initial; background-origin: initial; background-clip: initial; background-color: transparent; vertical-align: baseline; color: #0066cc; text-decoration: none; background-position: initial initial; background-repeat: initial initial; padding: 0px; margin: 0px; border: 0px initial initial;" href="http://code.kynetx.com/">Read the latest on our dev blog</a>