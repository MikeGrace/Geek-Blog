---
title: Taking Screenshots In Selenium Using Ruby
date: 2010-10-13T20:47:04+00:00
author: MikeGrace
layout: post
permalink: /2010/10/taking-screenshots-in-selenium-using-ruby/
categories:
  - How to
  - Selenium
  - Web Design -Dev
tags:
  - How to
  - Ruby
  - Selenium
  - Testing
---
I LOVE being able to take screenshots of my Selenium tests as they are running!

Here&#8217;s how I take screenshots of my selenium tests running, written in Ruby:

  * Find the variable referencing the selenium driver. Might look something like this: <pre lang="ruby">@selenium_driver = Selenium::Client::Driver.new(.....</pre>

  * Wait for condition to take screenshot. Example: <pre lang="ruby">page.wait_for_element("//h1", {:timeout_in_seconds => 10})</pre>

  * Take screenshot. Example: <pre lang="ruby">@selenium_driver.capture_entire_page_screenshot(File.expand_path(File.dirname(__FILE__)) + 'screenshot1.png', '')</pre>
    
    or something simpler like:
    
    <pre lang="ruby">@selenium_driver.capture_entire_page_screenshot('~/Desktop/screenshot1.png', '')</pre>

[Selenium documentation](http://selenium-client.rubyforge.org/classes/Selenium/Client/GeneratedDriver.html#M000231) for using the capture screenshot function.