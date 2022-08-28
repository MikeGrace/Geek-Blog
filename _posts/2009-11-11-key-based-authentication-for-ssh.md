---
title: Key Based Authentication for SSH
date: 2009-11-11T19:45:02+00:00
author: MikeGrace
layout: post
permalink: /2009/11/key-based-authentication-for-ssh/
categories:
  - How to
  - Mac OS
  - Security
tags:
  - Apple
  - Bash
  - How to
  - Linux
  - Security
  - Terminal
  - Tools
  - Ubuntu
---
## What is key based authentication for ssh?

<img class="size-full wp-image-1075 alignleft" title="key" src="/assets/2009/11/3509344402_1d0bd80ec9_t.jpg" alt="key" width="100" height="100" />Key based authentication for SSH is a way to connect remotely to another computer/server using an encrypted file you HAVE and an optional password you KNOW to unlock the file. Key based authentication has the advantage of being more secure and/or more convenient.

### Why?

Password based authentication:
  
Logging in via password over SSH encrypts your password so it ends up looking like this:
  
`..t-:p.%.E.{..E..X7.@.@.~....s..............NXP...{W..!8..;.eh9..N......#....q..1f...:...D9R0 zy`
  
Because the password is encrypted, it won&#8217;t be seen in plain text over the wire which is good. If the password is short or simple enough, a hacker will be able to crack your password. Assuming the password is good enough, password based authentication&#8217;s strength comes from keeping that knowledge from others.

Key based authentication allows you to connect remotely using an encrypted file as a key instead of a password. Key based authentication gives you the option to <!--more-->lock the key with a password or not. Many choose not to lock the key with a password for convenience but, if the key ever gets stolen, the captor will be able to use the key without putting in a password to unlock it.

_Key based authentication is a very attractive remote authentication solution because it employs two factors of authentication: something you have and something you know. Getting someone&#8217;s password is fairly easy given enough time but getting a file from their computer and their password is much more difficult._

## HOW TO

### How to set up key based authentication on a linux server

#### Setting up key based ssh authentication consists of 4 steps.

1. Create public & private keys on your machine
  
2. Copy public key to server
  
3. Add public key on server to server&#8217;s authorized key list
  
4. Enjoy while protecting password & private key

##### 1. Create public & private keys on your machine

  * On your local machine, issue the following command into the terminal to create the directory to hold your public and private keys. If it tells you that the directory already exists that is just fine.

`mkdir ~./.ssh`

  * Navigate to recently created directory.

`cd ~/.ssh`

  * Start application that will help you generate keys.

`ssh-keygen`

  * Follow and answer prompts to create keys. Pressing enter will accept defaults for prompts and is fine for all prompts except for the prompt asking for a passphrase. Enter a password to lock the key from unauthorized use or leave blank to have no passphrase. Running through the program looks like this:

`mike:.ssh mike$ ssh-keygen<br />
Generating public/private rsa key pair.<br />
Enter file in which to save the key (/Users/mike/.ssh/id_rsa):<br />
Enter passphrase (empty for no passphrase):<br />
Enter same passphrase again:<br />
Your identification has been saved in /Users/mike/.ssh/id_rsa.<br />
Your public key has been saved in /Users/mike/.ssh/id_rsa.pub.<br />
The key fingerprint is:<br />
4a:3b:67:e0:82:b7:46:51:0b:b3:41:28:d4:9a:5d:f6 mike@mike<br />
The key's randomart image is:<br />
+--[ RSA 2048]----+<br />
|...o.            |<br />
|. ..+o.          |<br />
| .+ o*..         |<br />
| o .o .E         |<br />
|     .o S        |<br />
|   ..o +         |<br />
|  ..o = o        |<br />
|   ..o +         |<br />
|   ..            |<br />
+-----------------+`

##### 2. Copy public key to server

  * Connect to server via ssh (or other means)

`ssh user@host`

  * Make folder to hold public key

`mkdir ~/.ssh`

  * Open new terminal window to copy public key to server via scp

`scp ~/.ssh/id_rsa.pub user@host:~/.ssh/`

  * Close terminal window used to copy public key over

##### 3. Add public key on server to server&#8217;s authorized key list

 `cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys`

##### 4. Enjoy while protecting password & private key

  * You are now all set up and can connect to the server using you newly created keys. Just ssh into the server as usual and the server will take care of the key authentication behind the scenes. If you are using a password to lock your key, you will see a window similar to this the first time you use the key until your mac keychain locks again. If you are not using a password to lock the key then you will never be prompted for a password again to ssh into your server from your computer.

<img class="alignnone size-full wp-image-1074" title="keys" src="/assets/2009/11/3466560105_0b6f694d4a_m.jpg" alt="keys" width="240" height="161" />

Note:
  
You can easily rename the keys so you can have multiple keys on a computer and server. Just make sure to append each key to the server&#8217;s authorized_keys file using
  
 `cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys`

I originally learned how to set up key based authentication on a linux server from my friend Jesse on his blog <http://www.jessecole.org/>

Images:

<div>
  <a rel="cc:attributionURL" href="http://www.flickr.com/photos/brenda-starr/">Keys </a> / <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">CC BY 2.0</a>
</div>

<div>
  <a rel="cc:attributionURL" href="http://www.flickr.com/photos/brenda-starr/">Key </a> / <a rel="license" href="http://creativecommons.org/licenses/by/2.0/">CC BY 2.0</a>
</div>