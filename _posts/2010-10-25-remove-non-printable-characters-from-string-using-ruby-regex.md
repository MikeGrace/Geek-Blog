---
title: Remove Non Printable Characters From String Using Ruby Regex
date: 2010-10-25T15:14:51+00:00
author: MikeGrace
layout: post
permalink: /2010/10/remove-non-printable-characters-from-string-using-ruby-regex/
categories:
  - How to
  - Selenium
tags:
  - regex
  - Ruby
  - Selenium
---
<figure style="width: 500px" class="wp-caption alignnone">[<img src="https://mikegrace.s3.amazonaws.com/geek-blog/printer-chain.jpg" alt="non printable characters" width="500" height="333" />](http://www.flickr.com/photos/mwichary/3339740020/)<figcaption class="wp-caption-text">non printable characters</figcaption></figure> 

I Recently was working on building some Selenium tests and needed to compare a string after being saved to a database and returned to the user interface. Because of the interface plugin that does some syntax highlighting, the string was being displayed with some non printable characters. Because the non printable characters were not breaking the app, I decided that it would be OK for me to remove them to compare the strings in my selenium test.

To remove the non printable characters or only return the printable characters I used the following ruby:

<pre lang="ruby">printableString = stringFromInterface.scan(/[[:print:]]/).join</pre>

There is a great list of other character classes that can be used in your regular expressions found at [http://doc.infosnel.nl/ruby\_regular\_expressions.html](http://doc.infosnel.nl/ruby_regular_expressions.html)

## Character classes

<table style="border-collapse: collapse;" border="0">
  <tr>
    <td style="text-align: center; border-bottom-width: 2px; border-bottom-style: solid; border-bottom-color: #3366cc; padding-top: 2px; padding-right: 1em; padding-bottom: 2px; padding-left: 1em; vertical-align: bottom; font-weight: bold;">
      Class
    </td>
    
    <td style="text-align: center; border-bottom-width: 2px; border-bottom-style: solid; border-bottom-color: #3366cc; padding-top: 2px; padding-right: 1em; padding-bottom: 2px; padding-left: 1em; vertical-align: bottom; font-weight: bold;">
      Switch
    </td>
    
    <td style="text-align: center; border-bottom-width: 2px; border-bottom-style: solid; border-bottom-color: #3366cc; padding-top: 2px; padding-right: 1em; padding-bottom: 2px; padding-left: 1em; vertical-align: bottom; font-weight: bold;">
      Match description
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[0-9]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>\d</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Decimal digit character
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[^0-9]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>\D</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Not a decimal digit character
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[\s\t\r\n\f]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>\s</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Whitespace character
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[^\s\t\r\n\f]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>\S</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Not a whitespace character
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[A-Za-z0-9_]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>\w</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Word character (alpha, numeric, and underscore)
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[^A-Za-z0-9_]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>\W</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Not a word character
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:alnum:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Alpha numeric (<tt>[A-Za-z0-9]</tt>)
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:alpha:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Uppercase and lowercase letters (<tt>[A-Za-z]</tt>)
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:blank:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Blank or tab character
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:space:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Whitespace characters
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:digit:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Decimal digit characters
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:lower:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Lowercase letters (<tt>[a-z]</tt>)
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:upper:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Uppercase characters
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:print:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Any printable character, including space
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:graph:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Printable characters excluding space
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:punct:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Punctuation characters: any printable character excluding aplhanumeric or space
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:cntrl]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Chontrol characters (0x00 to 0x1F and 0x7F)
    </td>
  </tr>
  
  <tr>
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      <tt>[:xdigit:]</tt>
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
    </td>
    
    <td style="background-color: #ecf9e5; border-bottom-width: 1px; border-bottom-style: groove; border-bottom-color: black; padding: 5px;">
      Hexadecimal digits (<tt>[0-9a-fA-F]</tt>)
    </td>
  </tr>
</table>