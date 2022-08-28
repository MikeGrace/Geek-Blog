---
title: Setup Gmail Like Plus Addressing on Shared Cpanel Hosting
date: 2015-05-12T14:04:57+00:00
author: MikeGrace
layout: post
permalink: /2015/05/setup-gmail-like-plus-addressing-on-shared-cpanel-hosting/
categories:
  - How to
tags:
  - How to
---
I have become a big fan of the plus addressing feature that Gmail offers. I had a client that wanted to be able to use this feature but was using the basic shared Cpanel hosting for email. We figured out how to can set things up in Cpanel to at least get the routing to act the same. **Note: You will have to create routing rules for each address you want this to work on.**

1) Make sure the default address is set up to catch emails (which is probably the biggest downside to this approach).

[<img class="alignnone wp-image-2437 size-medium" src="/assets/2015/05/Screen_Shot_2015-05-12_at_12_44_20_PM-300x155.jpg" alt="Screen_Shot_2015-05-12_at_12_44_20_PM" width="300" height="155" srcset="/assets/2015/05/Screen_Shot_2015-05-12_at_12_44_20_PM-300x155.jpg 300w, /assets/2015/05/Screen_Shot_2015-05-12_at_12_44_20_PM.jpg 523w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2015/05/Screen_Shot_2015-05-12_at_12_44_20_PM.jpg)

&nbsp;

2) Make sure the default address forwards to the main system account.

&nbsp;

[<img class="alignnone size-medium wp-image-2438" src="/assets/2015/05/Screen_Shot_2015-05-12_at_12_44_30_PM-300x283.jpg" alt="Screen_Shot_2015-05-12_at_12_44_30_PM" width="300" height="283" srcset="/assets/2015/05/Screen_Shot_2015-05-12_at_12_44_30_PM-300x283.jpg 300w, /assets/2015/05/Screen_Shot_2015-05-12_at_12_44_30_PM.jpg 339w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2015/05/Screen_Shot_2015-05-12_at_12_44_30_PM.jpg)

&nbsp;

3) Select &#8220;Manage Filters&#8221; for the main system account set in the previous step

&nbsp;

[<img class="alignnone size-medium wp-image-2439" src="/assets/2015/05/Screen_Shot_2015-05-12_at_12_45_00_PM-300x167.jpg" alt="Screen_Shot_2015-05-12_at_12_45_00_PM" width="300" height="167" srcset="/assets/2015/05/Screen_Shot_2015-05-12_at_12_45_00_PM-300x167.jpg 300w, /assets/2015/05/Screen_Shot_2015-05-12_at_12_45_00_PM.jpg 674w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2015/05/Screen_Shot_2015-05-12_at_12_45_00_PM.jpg)

&nbsp;

4) Setup filter rules by setting filter name
  
5) Set filter field to &#8220;To&#8221;
  
6) Set filter match operator to &#8220;contains&#8221;
  
7) Set action to &#8220;Redirect to Email&#8221;
  
8) Input email address to forward to

&nbsp;

[<img class="alignnone size-medium wp-image-2440" src="/assets/2015/05/Screen_Shot_2015-05-12_at_12_46_34_PM-300x219.jpg" alt="Screen_Shot_2015-05-12_at_12_46_34_PM" width="300" height="219" srcset="/assets/2015/05/Screen_Shot_2015-05-12_at_12_46_34_PM-300x219.jpg 300w, /assets/2015/05/Screen_Shot_2015-05-12_at_12_46_34_PM.jpg 576w" sizes="(max-width: 300px) 100vw, 300px" />](/assets/2015/05/Screen_Shot_2015-05-12_at_12_46_34_PM.jpg)

&nbsp;

9) Save by clicking &#8220;Create&#8221; and send a test email to confirm the filter is working.

&nbsp;