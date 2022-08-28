---
title: Validating Bank Routing Numbers In JavaScript
date: 2013-12-17T10:04:45+00:00
author: MikeGrace
layout: post
permalink: /2013/12/validating-bank-routing-numbers-in-javascript/
categories:
  - How to
  - JavaScript
tags:
  - JavaScript
---
TLDR;
  
Example code at <http://sandbox.michaelgrace.org/bank-routing-number-validation/>

I have a test script at <http://sandbox.michaelgrace.org/bank-routing-number-validation/> that I recently updated. I am having a hard time finding good documentation on it but ABA routing numbers that start with the number 5 are not valid. Routing numbers that start with 5 are internal bank routing numbers and are not valid for ACH transfers. Customers will often not realize that the routing number on their checks and the routing numbers on their bank deposit slips are different.

Here are the checks that I am doing in my JavaScript example:

  * routing number is a number
  * is 9 numbers in length
  * does not start with the number 5
  * checksum of routing number validates

For more information on the checksum for ABA routing numbers, check out [wikipedia](http://en.wikipedia.org/wiki/Routing_transit_number#MICR_Routing_number_format).

References for routing numbers starting with 5 being internal routing numbers:

https://firstib.custhelp.com/app/answers/detail/a_id/596
  
http://productforums.google.com/forum/#!topic/checkout-merchant/9XeAX4LAlqY
  
http://www.colorado.gov/pacific/osc/direct-deposits