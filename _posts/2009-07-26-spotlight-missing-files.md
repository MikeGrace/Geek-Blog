---
title: Spotlight Missing Files
date: 2009-07-26T01:53:44+00:00
author: MikeGrace
layout: post
permalink: /2009/07/spotlight-missing-files/
categories:
  - How to
  - Mac OS
---
<h3 style="text-align: center;">
  <figure id="attachment_543" style="width: 128px" class="wp-caption alignright"><img class="size-full wp-image-543 " title="spotlight_icon" src="/assets/2009/07/spotlight_icon.jpg" alt="Spotlight Icon" width="128" height="128" /><figcaption class="wp-caption-text">Spotlight Icon</figcaption></figure> 
  
  <p>
    How to fix your spotlight woes.</h3> 
    
    <p>
      I use spotlight all the time to launch applications and open files. I recently ran into some trouble with files and applications disappearing from the spotlight index. I was able to fix the problem by deleting my spotlight index and rebuilding it. <!--more-->
    </p><figure id="attachment_528" style="width: 500px" class="wp-caption aligncenter">
    
    <img class="size-full wp-image-528" title="preferences_spotlight" src="/assets/2009/07/preferences_spotlight.jpg" alt="System Preferences - Spotlight" width="500" height="116" srcset="/assets/2009/07/preferences_spotlight.jpg 500w, /assets/2009/07/preferences_spotlight-300x69.jpg 300w" sizes="(max-width: 500px) 100vw, 500px" /><figcaption class="wp-caption-text">System Preferences - Spotlight</figcaption></figure> 
    
    <p>
      First you should just make sure your spotlight settings haven&#8217;t caused the problem before you take the time to delete and rebuild your spotlight index. In system preferences go to spotlight. There are two tabs: Search Results and Privacy. Make sure the type of file you are looking for is selected and under privacy make sure the file isn&#8217;t located in any of the locations specified. Any location specified in the privacy tab will not be indexed.
    </p><figure id="attachment_530" style="width: 300px" class="wp-caption aligncenter">
    
    <img class="size-full wp-image-530" title="spotlight_search_results" src="/assets/2009/07/spotlight_search_results.jpg" alt="Spotlight Search Results Preferences" width="300" height="225" /><figcaption class="wp-caption-text">Spotlight Search Results Preferences</figcaption></figure> <figure id="attachment_529" style="width: 300px" class="wp-caption aligncenter"><img class="size-full wp-image-529" title="spotlight_privacy" src="/assets/2009/07/spotlight_privacy.jpg" alt="Spotlight Privacy Preferences" width="300" height="227" /><figcaption class="wp-caption-text">Spotlight Privacy Preferences</figcaption></figure> 
    
    <h3>
      Delete and Rebuild Spotlight Index
    </h3>
    
    <p>
      To delete and rebuild your spotlight index open up your terminal and enter in these commands. (You will need your root password to execute these commands)
    </p>
    
    <pre><code>&lt;span>sudo rm &lt;/span>&lt;span>-&lt;/span>&lt;span>r &lt;/span>&lt;span>/.&lt;/span>&lt;span>Spotlight&lt;/span>&lt;span>-&lt;/span>&lt;span>V&lt;/span>&lt;span>100&lt;/span>&lt;span>
sudo launchctl load &lt;/span>&lt;span>-&lt;/span>&lt;span>w &lt;/span>&lt;span>/&lt;/span>&lt;span>System&lt;/span>&lt;span>/&lt;/span>&lt;span>Library&lt;/span>&lt;span>/&lt;/span>&lt;span>LaunchDaemons&lt;/span>&lt;span>/&lt;/span>&lt;span>com&lt;/span>&lt;span>.&lt;/span>&lt;span>apple&lt;/span>&lt;span>.&lt;/span>&lt;span>metadata&lt;/span>&lt;span>.&lt;/span>&lt;span>mds&lt;/span>&lt;span>.&lt;/span>&lt;span>plist
sudo mdutil &lt;/span>&lt;span>-&lt;/span>&lt;span>E &lt;/span>&lt;span>/&lt;/span></code></pre>
    
    <p>
      NOTE: For most, copying and pasting these commands will  work just fine. For some of you it might come back on the first command that the file was not found. If this is the case for you it&#8217;s ok, we just need to find the right file. Paste the first line all the way up to the &#8220;V&#8221; like this:
    </p>
    
    <pre><code>&lt;span>sudo rm &lt;/span>&lt;span>-&lt;/span>&lt;span>r &lt;/span>&lt;span>/.&lt;/span>&lt;span>Spotlight&lt;/span>&lt;span>-&lt;/span>&lt;span>V&lt;/span></code></pre>
    
    <p>
      then just hit the tab key and it should complete the file name. You can now hit enter and paste the rest of the commands with no problem.
    </p>
    
    <h3>
      Explained
    </h3>
    
    <ol>
      <li>
        Deletes the spotlight index file
      </li>
      <li>
        Sends secret message to the elves in your computer that make things happen
      </li>
      <li>
        Causes Spotlight to rebuild indexes
      </li>
    </ol>
    
    <p>
      After you have rebuilt the index, you and spotlight can live happily ever after. :)
    </p>
    
    <p>
      <img class="aligncenter size-full wp-image-537" title="holding_hands_sunset" src="/assets/2009/07/holding_hands_sunset.jpg" alt="holding_hands_sunset" width="500" height="125" srcset="/assets/2009/07/holding_hands_sunset.jpg 500w, /assets/2009/07/holding_hands_sunset-300x75.jpg 300w" sizes="(max-width: 500px) 100vw, 500px" /><br /> Resources:<br /> Sunset Image: <a rel="cc:attributionURL" href="http://www.flickr.com/photos/mikebaird/">http://www.flickr.com/photos/mikebaird/</a> / <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">CC BY 2.0</a><br /> Terminal commands: <a href="http://superuser.com/questions/8414/stuff-dissapearing-from-spotlight-search">Question I asked on superuser.com</a>
    </p>