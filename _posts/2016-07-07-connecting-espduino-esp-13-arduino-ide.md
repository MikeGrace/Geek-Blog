---
title: Connecting ESPDUINO (ESP-13) to Arduino IDE
date: 2016-07-07T09:00:46+00:00
author: MikeGrace
layout: post
permalink: /2016/07/connecting-espduino-esp-13-arduino-ide/
categories:
  - Arduino
  - How to
tags:
  - How to
---
https://github.com/esp8266/Arduino was the most helpful place to start. You need to

  * open the Arduino IDE
  * Open &#8216;Preferences&#8217; menu under &#8216;File&#8217;
  * Add the url http://arduino.esp8266.com/stable/package\_esp8266com\_index.json to the &#8216;Additional Boards Manager URLs&#8217; input box
  * click &#8216;OK&#8217;
  * open menus &#8216;Tools&#8217; -> &#8216;Board&#8217; -> &#8216;Boards Manager&#8217;
  * find the esp8266 by searching in search filter input
  * Click the esp8266 and click install

You should then be able to connect to and upload sketches to the espduino board.