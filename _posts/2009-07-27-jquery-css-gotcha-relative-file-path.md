---
title: jQuery CSS Gotcha with Relative File Paths
date: 2009-07-27T22:16:09+00:00
author: MikeGrace
layout: post
permalink: /2009/07/jquery-css-gotcha-relative-file-path/
aktt_notify_twitter:
  - 'yes'
aktt_tweeted:
  - "1"
categories:
  - Web Design -Dev
---
[<img class="alignleft size-full wp-image-582" title="gotcha" src="/assets/2009/07/3521287388_2dc77cf3e5_m.jpg" alt="gotcha" width="240" height="133" />](http://www.flickr.com/photos/saranv/3521287388/)jQuery gave a colleague and I a run for our money today at work. We were using jQuery to change the background image after a mouse event. Problem was, after the event, the image would not show up even though the path to the image was *correct. <!--more-->Our site is set up so the html files are at the root with css and images in their own folders off of the root folder. The external CSS for the background image:


  
`background-image: url('../images/background.jpg');`
  
Without thinking much about it, I set jQuery to change the CSS path to the other image just like in the external CSS file`$('#background_spot').css('backgroundImage',"url('../images/event_background.jpg')");`Every time the event would fire the path would be changed but there would be no image. Argggg! (cue the head scratching here) After a few minutes of wondering what was wrong with me and talking to myself it finally dawned on me&#8230;

### Gotcha&#8230;

jQuery changes CSS inline rather than to an external CSS document meaning that my relative path was invalid. My jQuery CSS image path needed to be `$('#background_spot').css('backgroundImage',"url('images/event_background.jpg')");`
  
After making the change for the path of the image to be from the html file we were all smiles.[<img class="size-full wp-image-587 aligncenter" title="all smiles" src="/assets/2009/07/2765083201_e0958937bf_m.jpg" alt="all smiles" width="240" height="159" />](http://www.flickr.com/photos/dotbenjamin/2765083201/)
  
Photos:
  
<a rel="cc:attributionURL" href="http://www.flickr.com/photos/saranv/">http://www.flickr.com/photos/saranv/</a> / <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">CC BY 2.0</a>
  
<a rel="cc:attributionURL" href="http://www.flickr.com/photos/dotbenjamin/">http://www.flickr.com/photos/dotbenjamin/</a> / <a rel="license" href="http://creativecommons.org/licenses/by-sa/2.0/">CC BY-SA 2.0</a>