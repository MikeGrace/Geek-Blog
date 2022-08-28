---
title: Disable Skype Auto Mic Adjustment On Mac
date: 2011-03-30T22:49:33+00:00
author: MikeGrace
layout: post
permalink: /2011/03/disable-skype-auto-mic-adjustment-on-mac/
categories:
  - How to
tags:
  - skype
---
If you have ever been frustrated with Skype automatically changed the input volume for your microphone you can turn it off. 

For Skype versions prior to 5 there is this blog post on how to do it <http://hints.macworld.com/article.php?story=20081116113445565>

For Skype version 5&#8230;

Open up the file found at ~/Library/Application Support/Skype/shared.xml

At the bottom of the file you should see something like

<pre lang="bash">&lt;VoiceEng>
  &lt;MicBoost>
    &lt;_260>-1&lt;/_260>
  &lt;/MicBoost>
  &lt;MicVolume>
    &lt;_260>73&lt;/_260>
    &lt;AppleHDAEngineInput.3A8.2C0.2C1.2C0.3A1>81&lt;/AppleHDAEngineInput.3A8.2C0.2C1.2C0.3A1>
    &lt;AppleHDAEngineInput.3A8.2C0.2C1.2C1.3A2>100&lt;/AppleHDAEngineInput.3A8.2C0.2C1.2C1.3A2>
  &lt;/MicVolume>
  &lt;SpeakerVolume>68&lt;/SpeakerVolume>
&lt;/VoiceEng>
</pre>

Change the value inside of the &#8216;MicBoost&#8217; and _260 blocks to 0 and that should turn the auto adjusting off.

I also changed the volume to 100 so it is all the way up so I can control the input from my system preferences. In the end yours should end up looking something like this

<pre lang="bash">&lt;VoiceEng>
  &lt;MicBoost>
    &lt;_260>0&lt;/_260>
  &lt;/MicBoost>
  &lt;MicVolume>
    &lt;_260>100&lt;/_260>
    &lt;AppleHDAEngineInput.3A8.2C0.2C1.2C0.3A1>63&lt;/AppleHDAEngineInput.3A8.2C0.2C1.2C0.3A1>
    &lt;AppleHDAEngineInput.3A8.2C0.2C1.2C1.3A2>100&lt;/AppleHDAEngineInput.3A8.2C0.2C1.2C1.3A2>
  &lt;/MicVolume>
  &lt;SpeakerVolume>68&lt;/SpeakerVolume>
&lt;/VoiceEng>
</pre>