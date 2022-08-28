---
title: 'Could not connect to database&#8230; old insecure authentication'
date: 2014-05-28T00:41:27+00:00
author: MikeGrace
layout: post
permalink: /2014/05/could-not-connect-to-database-old-insecure-authentication/
categories:
  - How to
---
Error:

> <span style="color: #000000;">Could not connect to database. SQLSTATE[HY000] [2000] mysqlnd cannot connect to MySQL 4.1+ using the old insecure authentication. Please use an administration tool to reset your password with the command SET PASSWORD = PASSWORD(&#8216;your_existing_password&#8217;). This will store a new, and more secure, hash value in mysql.user. If this user is used in other scripts executed by PHP 5.2 or earlier you might need to remove the old-passwords flag from your my.cnf file</span>

Solution:

run the following SQL to update the password

<pre><span style="color: #000000;">SET SESSION old_passwords = 0;
SET PASSWORD = PASSWORD('replace_with_correct_password');

</span></pre>

Example using Sequel Pro

<img class="alignnone" src="http://mikegrace.s3.amazonaws.com/geek-blog/update-password.jpg" alt="" width="600" height="435" />