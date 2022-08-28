---
title: Escaping Ruby Strings For Eval In Selenium Tests
date: 2010-10-11T18:29:19+00:00
author: MikeGrace
layout: post
permalink: /2010/10/escaping-ruby-strings-for-eval-in-selenium-tests/
categories:
  - How to
  - Selenium
  - Web Design -Dev
tags:
  - Ruby
  - Selenium
  - Strings
  - Testing
---
If you are setting up a string in Ruby to then be used in an eval statement in a Selenium test you&#8217;ll need some escaping fu to be able to pull it off.

Quotes in strings that are then going to be put in other Ruby strings need to be tripple escaped. If the string is going directly to the eval in Selenium then only a single escape is needed.

<pre lang="javascript">first = "first quote: \\\"......"
second = "#{first} second quote: \\\".........."
jsfunction = "window.alert(\"#{second}\")"
puts jsfunction

it "should alert string" do
  page.js_eval(jsfunction)
end
</pre>

![selenuim ruby string escaping for eval](https://mikegrace.s3.amazonaws.com/geek-blog/selenuin-ruby-string-escaping.png)