---
title: IMAP email UID vs Message Sequence Number
date: 2012-02-09T12:50:11+00:00
author: MikeGrace
layout: post
permalink: /2012/02/imap-email-uid-vs-message-sequence-number/
categories:
  - Web Design -Dev
tags:
  - email
  - imap
---
[<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/email-uid-vs-msn.jpg" alt="" width="624" height="229" />](http://mikegrace.s3.amazonaws.com/geek-blog/email-uid-vs-msn.jpg)

I&#8217;ve had the chance to play around with some email code recently and it&#8217;s been fun. Here is something that I learned that I think should be easier to find for those who are getting into writing an app that handles emails via IMAP.

**What is the difference between an email&#8217;s _Unique Identifier_ (UID) and an emails&#8217;s _Message Sequence Number_ (MSN?).**

  * Unique Identifier: A unique number referencing an email that does not change over time
  * Message Sequence Number: The relative position from the first message in the mailbox

You can read more about this exciting IMAP email topic at <http://www.faqs.org/rfcs/rfc3501.html>