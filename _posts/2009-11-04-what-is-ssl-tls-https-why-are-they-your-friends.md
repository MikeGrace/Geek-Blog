---
title: 'What is SSL, TLS, https &#038; why are they your friends?'
date: 2009-11-04T03:55:26+00:00
author: MikeGrace
layout: post
permalink: /2009/11/what-is-ssl-tls-https-why-are-they-your-friends/
categories:
  - Security
tags:
  - Browser
  - Security
---
<p style="text-align: center;">
  <a href="http://www.flickr.com/photos/bala_/2535158091/"><img class="aligncenter size-full wp-image-1027" title="security" src="/assets/2009/11/2535158091_bd4439f69b.jpg" alt="security" width="487" height="231" srcset="/assets/2009/11/2535158091_bd4439f69b.jpg 487w, /assets/2009/11/2535158091_bd4439f69b-300x142.jpg 300w" sizes="(max-width: 487px) 100vw, 487px" /></a>Do you know what SSL, TLS, and https mean and do? You deal with SSL, TLS, and https whether you know it or not and it is very important!
</p>

TLS = Transport Layer Security
  
SSL = Secure Socket Layer
  
https = Hypertext Transfer Protocol Secure

Private and sensitive information gets sent over the internet all day so what is preventing someone from stealing that information? In order for information to be securely transferred over the internet 2 basics are needed.
  
1. Confirm server identity
  
2. Encrypt communication with server[<img class="alignright size-full wp-image-1021" title="Identity" src="/assets/2009/11/2236491509_2c82f1926d_m.jpg" alt="Identity" width="144" height="125" />](http://www.flickr.com/photos/narciss/2236491509/)

You don&#8217;t want to send information to someone who is impersonating the person you actually want to send it to, do you? SSL and TLS provide a way to verify the identity of the recipient. In it&#8217;s simplest form, there are many companies that will give people digitally signed certificates vouching for that person saying in essence, &#8220;we have checked to make sure this person is who they say they are and we think you can trust them.&#8221; When you browse the web, your browser has a list of companies that it will trust to tell you who you can trust. So, when you connect to a server your browser can check their certificate and if it is signed by one of the companies that you trust then your browser will trust it.

Private conversations are good when you are sharing sensitive or private data. You don&#8217;t go walking around on the street shouting out your birthday, credit card number, and social security number so why would you do it on the internet? [<img class="size-full wp-image-1023 alignleft" title="shouting" src="/assets/2009/11/2336528544_12c8c64896_m.jpg" alt="shouting" width="240" height="183" />](http://www.flickr.com/photos/demibrooke/2336528544/)TLS and SSL provide a way for you to have a private conversation with a server so that others can&#8217;t &#8220;listen in&#8221; on your conversation by encrypting the data. Most data on the web is transferred using http but when it is secured using TLS or SSL it is called https.

It&#8217;s important to know when you are or aren&#8217;t using https when browsing the web to protect your information. Most browsers have visual indicators to show that https is being used. Make it a habit to make sure that your information will be secure before sending or retrieving that data.

Resources to learn more of the nitty gritty of SSL, TLS, and https
  
TLS:
  
[http://en.wikipedia.org/wiki/Transport\_Layer\_Security](http://en.wikipedia.org/wiki/Transport_Layer_Security)
  
 [](http://en.wikipedia.org/wiki/Transport_Layer_Security)<http://www.ietf.org/dyn/wg/charter/tls-charter.html>

SSL:
  
 [](http://en.wikipedia.org/wiki/Transport_Layer_Security)<http://www.verisign.com/ssl/ssl-information-center/how-ssl-security-works/index.html>
  
 [](http://video.google.com/videoplay?docid=7130470471741831613&ei=JETxSrXaC5v-qAPLzKWxDQ&q=ssl&hl=en&view=2&client=firefox-a#)<http://video.google.com/videoplay?docid=7130470471741831613&ei=JETxSrXaC5v-qAPLzKWxDQ&q=ssl&hl=en&view=2&client=firefox-a#>

https:
  
 [](http://video.google.com/videoplay?docid=7130470471741831613&ei=JETxSrXaC5v-qAPLzKWxDQ&q=ssl&hl=en&view=2&client=firefox-a#)<http://en.wikipedia.org/wiki/HTTP_Secure>
  
 [](http://video.google.com/videoplay?docid=7130470471741831613&ei=JETxSrXaC5v-qAPLzKWxDQ&q=ssl&hl=en&view=2&client=firefox-a#)<http://www.ourshop.org/resources/ssl.html>

Images <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">via CC BY 2.0</a>
  
Lock and Chain: <a rel="cc:attributionURL" href="http://www.flickr.com/photos/bala_/">http://www.flickr.com/photos/bala_/</a>
  
Silheuette: <a rel="cc:attributionURL" href="http://www.flickr.com/photos/narciss/">http://www.flickr.com/photos/narciss/</a>
  
Yelling: <a rel="cc:attributionURL" href="http://www.flickr.com/photos/demibrooke/">http://www.flickr.com/photos/demibrooke/</a>