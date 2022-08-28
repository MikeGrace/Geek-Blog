---
title: Java Global Exception Handling
date: 2011-09-07T09:56:56+00:00
author: MikeGrace
layout: post
permalink: /2011/09/java-global-exception-handling/
categories:
  - Java
tags:
  - 30 days of java
---
It&#8217;s been a while since I have worked with Java and it&#8217;s time for me to brush up so I have decided to do 30 days of Java. I will be attempting to learn something new or explain something about Java each day.

In many of my projects I use a remote error collecting service called [ErrorStack](http://www.errorstack.com/). Love it! My apps throw errors over the internet to it and it generates report and has a myriad of ways to alert me. I do my best to write code that doesn&#8217;t have errors and handles errors and exception gracefully but it still happens. This is where the Java 1.5 [setDefaultUncaughtExceptionHandler](http://download.oracle.com/javase/1.5.0/docs/api/java/lang/Thread.html#setDefaultUncaughtExceptionHandler(java.lang.Thread.UncaughtExceptionHandler)) comes in to play.

I wrote some quick code to test out the feature

<pre lang="java">package org.michaelgrace.sandbox;

public class GlobalErrorHandling {

  public static void main(String[] args) {
    Handler handler = new Handler();
    Thread.setDefaultUncaughtExceptionHandler(handler);
    
    throw new RuntimeException("party on error!");
  }
}

class Handler implements Thread.UncaughtExceptionHandler {
  public void uncaughtException(Thread t, Throwable e) {
    System.out.println("Where did that error come from?!");
    System.out.println("This is where I would report the error to ErrorStack");
    System.out.println(e.getMessage());
    System.out.println(t.toString());
  }
}</pre>

I exported the class to a [jar](http://mikegrace.s3.amazonaws.com/geek-blog/global-error-test.jar) using Eclipse and ran it from the command line

<pre lang="bash">mgrace$ java -jar global-error-test.jar 
Where did that error come from?!
This is where I would report the error to ErrorStack
party on error!
Thread[main,5,main]</pre>

It worked!

I plan on building a class for making it easy to report errors to ErrorStack and will release it to the world when I do.

Resources: <http://www.nomachetejuggling.com/2006/06/13/java-5-global-exception-handling/>