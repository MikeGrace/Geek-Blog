---
title: Cloned WordPress Redirecting Back To Original
date: 2012-05-18T10:24:50+00:00
author: MikeGrace
layout: post
permalink: /2012/05/cloned-wordpress-redirecting-back-to-original/
categories:
  - How to
  - Web Design -Dev
  - WordPress
---
<img class="aligncenter" title="WordPress Admin Redirecting" src="http://mikegrace.s3.amazonaws.com/geek-blog/wordpress-admin-redirect.jpg" alt="WordPress Admin Redirecting" width="433" height="435" />

Was recently working on a WordPress instance for a client where we have a cloned version of the production installation in dev. Since WordPress stores its settings in the database it would redirect to the production instance when I tried to log into the WordPress admin on the dev instance. Thankfully, the fix was fairly simple.

  * SSHed into the dev instance
  * logged into MySQL database
  * updated &#8216;wp\_options&#8217; table rows where &#8216;option\_name&#8217; is &#8216;siteurl&#8217; and &#8216;home&#8217; and set it to the dev url instead of the production url