---
title: Get Firefox Add-ons to Work with ALL Versions of Firefox
date: 2009-08-18T01:23:16+00:00
author: MikeGrace
layout: post
permalink: /2009/08/get-firefox-add-ons-to-work-with-all-versions-of-firefox/
aktt_notify_twitter:
  - 'no'
categories:
  - Firefox
  - How to
  - Web Design -Dev
tags:
  - Add-on
  - Browser
  - Firefox
  - How to
  - Tools
---
[<img class="alignleft size-full wp-image-832" title="The way you feel when you realize your favorite add-on is incompatible" src="/assets/2009/08/shock.jpg" alt="The way you feel when you realize your favorite add-on is incompatible" width="250" height="250" srcset="/assets/2009/08/shock.jpg 250w, /assets/2009/08/shock-150x150.jpg 150w" sizes="(max-width: 250px) 100vw, 250px" />](http://www.flickr.com/photos/carbonnyc/2206470413/)Ever upgraded to the next version of Firefox and your add-on didn&#8217;t show up because it was marked &#8220;Not Compatible&#8221;? There is a very simple way to force your version of Firefox to accept the add-on even if it isn&#8217;t compatible.

There are a few reasons why your installed add-ons might get marked as incompatible. Sometimes the developer has not changed the install requirements to accept your version. Mozilla suggests to developers that they don&#8217;t mark it compatible until they KNOW it is compatible. So, many developers don&#8217;t mark their add-ons compatible with beta and alpha releases of Firefox. Another reason an add-on might not be marked as compatible is because it really ISN&#8217;T compatible. Running an incompatible add-on can corrupt data in your browser profile and other places on your computer so don&#8217;t force add-ons to work unless you are willing to deal with the risks.

<p style="text-align: center;">
  <img class="aligncenter size-full wp-image-834" title="Firefox 3.5, 3.6b, 3.7a" src="/assets/2009/08/all_three.png" alt="all_three" width="400" height="153" srcset="/assets/2009/08/all_three.png 400w, /assets/2009/08/all_three-300x114.png 300w" sizes="(max-width: 400px) 100vw, 400px" />
</p>

<!--more-->

#### Precautions:

  * Don&#8217;t force add-ons unless you are willing to deal with possible browser crashing and data/profile corruption!
  * Backup your profile!
  * Be an add-on minimalist! The more add-ons you have, the more that can go wrong&#8230; very wrong.
  * Backup your system regularly. If you don&#8217;t do this already your crazy and you should start yesterday!

#### How:

To force Firefox to accept all installed add-ons we simply need to tell it in it&#8217;s configuration file to ignore incompatibility. It will still check for updates and inform you that add-ons are incompatible, but it will let them run.

#### Steps:

  1. Open Firefox
  2. Type `about:config` into browser bar and press enter
  3. Click &#8220;I&#8217;ll be careful, I promise!&#8221; button and chuckle at Mozilla&#8217;s developer&#8217;s humor
  4. Right click on any list item in browser window and select &#8220;New&#8221; -> &#8220;Boolean&#8221;
  5. Paste `extensions.checkCompatibility` into alert box input window
  6. Select &#8220;False&#8221;
  7. Open add-ons window: Select &#8220;Tools&#8221; -> &#8220;Add-ons&#8221;
  8. Click &#8220;Restart&#8221; on yellow notification bar
  9. Throw your hands up in the air
 10. Shout for joy
 11. Spin around in your twirly chair and get back to work
 12. ; )

#### Visual Steps:

  1. Click on the first image
  2. Click on the arrows that show up when you mouse over the image to walk through the steps visually
  3. Enjoy the show

<div id='gallery-1' class='gallery galleryid-794 gallery-columns-3 gallery-size-thumbnail'>
  <figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/00_non_compatability.jpg'><img width="150" height="150" src="/assets/2009/08/00_non_compatability-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/01_firefox_about_config.jpg'><img width="150" height="41" src="/assets/2009/08/01_firefox_about_config-150x41.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/02_ill_be_careful_i_promise.jpg'><img width="150" height="150" src="/assets/2009/08/02_ill_be_careful_i_promise-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/03_create_new_preference.jpg'><img width="150" height="150" src="/assets/2009/08/03_create_new_preference-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/04_config_preference_name.jpg'><img width="150" height="150" src="/assets/2009/08/04_config_preference_name-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/05_boolean_choice.jpg'><img width="150" height="150" src="/assets/2009/08/05_boolean_choice-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/06_extension.checkCompatibility.jpg'><img width="150" height="85" src="/assets/2009/08/06_extension.checkCompatibility-150x85.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/07_firefox_restart.jpg'><img width="150" height="131" src="/assets/2009/08/07_firefox_restart-150x131.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/08_forced_compatability.jpg'><img width="150" height="150" src="/assets/2009/08/08_forced_compatability-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/all_three.png'><img width="150" height="150" src="/assets/2009/08/all_three-150x150.png" class="attachment-thumbnail size-thumbnail" alt="" /></a>
  </div></figure><figure class='gallery-item'> 
  
  <div class='gallery-icon landscape'>
    <a href='/assets/2009/08/shock.jpg'><img width="150" height="150" src="/assets/2009/08/shock-150x150.jpg" class="attachment-thumbnail size-thumbnail" alt="" srcset="/assets/2009/08/shock-150x150.jpg 150w, /assets/2009/08/shock.jpg 250w" sizes="(max-width: 150px) 100vw, 150px" /></a>
  </div></figure>
</div>

Shocked Photo: <a rel="cc:attributionURL" href="http://www.flickr.com/photos/carbonnyc/">http://www.flickr.com/photos/carbonnyc/</a> / <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">CC BY 2.0</a>