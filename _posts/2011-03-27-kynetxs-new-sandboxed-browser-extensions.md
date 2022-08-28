---
title: 'Kynetx&#8217;s New Sandboxed Browser Extensions'
date: 2011-03-27T00:09:35+00:00
author: MikeGrace
layout: post
permalink: /2011/03/kynetxs-new-sandboxed-browser-extensions/
categories:
  - Chrome
  - Firefox
  - How to
  - JavaScript
  - Kynetx
tags:
  - Add-on
  - Browser
  - Chrome
  - extension
  - Firefox
  - How to
  - JavaScript
  - jQuery
  - Kynetx
  - sandbox
  - Twitter
---
I recently released my [&#8220;Old School Retweet&#8221; Kynetx app](http://apps.kynetx.com/installable_apps/1042-old-school-retweet) in the [Kynetx app store](http://apps.kynetx.com/) for the newly released browser extensions. I super love the new extensions and all that they do for users and developers alike. Something that I forgot when I released the app in the app store is that the new extension are sandboxed.

Because the extensions are sandboxed, all of the scripts from the extensions run a bit differently than they used to in the previous Kynetx extensions. Without getting into the technical details too much, the previous extensions just injected JavaScript into the page and the new extensions run JavaScript in a sandbox which has access to the DOM but can&#8217;t access anything else on the page. Because of this change my retweet app broke since I was using the jQuery loaded by Twitter.com to bring up the new tweet box (I do this because Twitter.com used that library to bind a click event and to trigger that event it has to be from the same library that bound it). Thankfully, with the help of a [friend](http://twitter.com/alexkolson), I was able to get a work around for both Firefox and Chrome&#8217;s sandbox environment.

How I did it&#8230;

If the app is run not inside a sandbox I can just access the jQuery that Twitter.com loads to open a new tweet box

<pre lang="javascript">$("#new-tweet").trigger("click");</pre>

From within the Firefox sandbox I can access the page outside of the sandbox 

<pre lang="javascript">window['$']("#new-tweet").trigger("click");</pre>

If I am in the Chrome sandbox I can create a script element that has the JavaScript that I want to execute. Crude, but it works. : )

<pre lang="javascript">var trigger_click_script = document.createElement("script");
var fallback = "window['$']('#new-tweet').trigger('click');";
trigger_click_script.innerHTML = fallback;
document.getElementsByTagName("head")[0].appendChild(trigger_click_script);</pre>

Here is the JavaScript code that I ended up with that gets executed when a user clicks on the retweet button.

<pre lang="Javascript">// get stuff to retweet
var tweet = $K(this).parents(".tweet-content").find(".tweet-text").text();
var name = $K(this).parents(".tweet-content").find(".tweet-screen-name").text();

// build tweet
var retweet = "RT @"+name+" "+tweet;

// open new tweet box
$("#new-tweet").trigger("click");

// hack for FF sandbox
if ($("#tweet-dialog:visible").length === 0) {
  window['$']("#new-tweet").trigger("click");
}

// put tweet in new tweet box
$K(".draggable textarea.twitter-anywhere-tweet-box-editor").val(retweet).focus();
$K("#tweet_dialog a.tweet-button.button.disabled").removeClass("disabled");

// hack for chrome sandbox
if ($("#tweet-dialog:visible").length === 0) {
  var fallback = "window['$']('#new-tweet').trigger('click'); ";
  fallback += "window['$']('.draggable textarea.twitter-anywhere-tweet-box-editor').val('"+retweet+"').focus(); ";
  fallback += "window['$']('#tweet_dialog a.tweet-button.button.disabled').removeClass('disabled'); ";
  var trigger_click_script = document.createElement("script");
  trigger_click_script.innerHTML = fallback;
  document.getElementsByTagName("head")[0].appendChild(trigger_click_script);
}</pre>