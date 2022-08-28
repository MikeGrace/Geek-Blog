---
title: Installing statsd on Ubuntu Server 10.04
date: 2011-09-05T19:42:22+00:00
author: MikeGrace
layout: post
permalink: /2011/09/installing-statsd-on-ubuntu-server-10-04/
categories:
  - How to
  - Linux
  - Web Design -Dev
---
![](http://mikegrace.s3.amazonaws.com/geek-blog/graphite-data-via-statsd.png.png)

Installing StatsD on an Ubuntu server (10.04) was surprisingly easy. Here are the steps that I took. These will work from a fresh install of Ubuntu server 10.04 or after having [installed and started graphite](http://geek.michaelgrace.org/2011/09/how-to-install-graphite-on-ubuntu/).

<pre lang="bash"># INSTALL NODE.JS
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python-software-properties git-core
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install nodejs

# CLONE THE STATSD PROJECT
git clone https://github.com/etsy/statsd.git

# CREATE A CONFIG FILE
cd statsd
cp exampleConfig.js dConfig.js
# edit config file your settings
sudo vim dConfig.js
node stats.js dConfig.js

# START STATSD
node stats.js dConfig.js</pre>

When you start StatsD, it will probably give you a warning like 

> (node) process.compile should not be used. Use require(&#8216;vm&#8217;).runInThisContext instead.

but it is still working as expected so you can ignore it.

You can then test to make sure StatsD is working. Edit and run this simple PHP script to throw some stats at your StatsD.

<pre lang="php"><?php

StatsD::increment("testing.increment");
StatsD::timing("testing.timing", 2345);

class StatsD {
    public static function timing($stat, $time, $sampleRate=1) {
        StatsD::send(array($stat => "$time|ms"), $sampleRate);
    }
    public static function increment($stats, $sampleRate=1) {
        StatsD::updateStats($stats, 1, $sampleRate);
    }
    public static function decrement($stats, $sampleRate=1) {
        StatsD::updateStats($stats, -1, $sampleRate);
    }
    public static function updateStats($stats, $delta=1, $sampleRate=1) {
        if (!is_array($stats)) { $stats = array($stats); }
        $data = array();
        foreach($stats as $stat) {
            $data[$stat] = "$delta|c";
        }
        StatsD::send($data, $sampleRate);
    }
    public static function send($data, $sampleRate=1) {
        $sampledData = array();
        if ($sampleRate &lt; 1) {
            foreach ($data as $stat => $value) {
                if ((mt_rand() / mt_getrandmax()) &lt;= $sampleRate) {
                    $sampledData[$stat] = "$value|@$sampleRate";
                }
            }
        } else {
            $sampledData = $data;
        }
        if (empty($sampledData)) { return; }
        try {
            $host = [your graphite host here];
            $port = [your graphite port here 8125?];
            $fp = fsockopen("udp://$host", $port, $errno, $errstr);
            if (! $fp) { return; }
            foreach ($sampledData as $stat => $value) {
                fwrite($fp, "$stat:$value");
            }
            fclose($fp);
        } catch (Exception $e) {
        }
    }
}

?></pre>

Be sure to edit the $host and $port settings towards the bottom with the appropriate graphite settings.

![](http://mikegrace.s3.amazonaws.com/geek-blog/statsd-graphite-graph.png)

When you run this script, you can run a tcpdump on the receiving machine to see if the UDP packets are getting to the machine. 

<pre lang="bash">sudo tcpdump -tn port 8125</pre>

If your StatsD is installed on a different machine/IP than Graphite, you can also watch StatsD send of the data by running

<pre lang="bash">sudo tcpdump -tn port 8125 or port 2003</pre>

This is especially helpful if you have not properly set up your Amazon EC2 security group settings. Be sure to open a UDP port for the traffic coming through.

![](http://mikegrace.s3.amazonaws.com/geek-blog/ec2-security-group-for-statsd.png)