---
title: Print Ubuntu Server IP or EC2 Public IP with Bash Script
date: 2011-09-19T11:53:52+00:00
author: MikeGrace
layout: post
permalink: /2011/09/print-ubuntu-server-ip-or-ec2-public-ip-with-bash-script/
categories:
  - EC2
  - How to
  - Ubuntu
---
How to get EC2 public IP from command line or bash script

Recently, while helping out with the [OpenPhoto](https://github.com/openphoto/frontend) project, I created a bash script that would print out the Ubuntu server&#8217;s IP address if it was not installed on Amazon&#8217;s EC2. If it is installed on EC2 it would get the publicly accessible IP address of the machine and print that out instead.

<pre lang="bash">#!/bin/bash
# finding IP address and compensating for possible EC2 installation
EC2=`curl --silent --connect-timeout 1 http://169.254.169.254/latest/meta-data/public-hostname`
if [[ $EC2 != "" ]]; 
then
    IP=`echo $EC2 | sed -rn 's/ec2-(.*?)\.compute.*/\1/p' | sed 's/-/./g'`
else
    IP=`ifconfig eth0 | grep 'inet addr:' | cut -d: -f2 | awk '{ print $1}'`
fi</pre>