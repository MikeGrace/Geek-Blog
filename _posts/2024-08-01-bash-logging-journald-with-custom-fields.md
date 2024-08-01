---
title: Bash Logging to Journald with Custom Fields
layout: post
categories:
  - linux
  - automation
---

I'm working on building out various automation scripts and I want to be able to easily track and troubleshoot all of them. Enter structured logging via Journald! Logging to journald via bash is not as easy as python and takes a bit extra work to ensure that it has similar fields as my python logging. Here is a simple example that I've created with a function to make it reusable throughout the script:

```bash
# Configure the logging
SCRIPT_NAME="journald-logging-example.sh"
CUSTOM_FIELDS="TAG=demo
CATEGORY=blog
LOGGER=${SCRIPT_NAME}
SYSLOG_IDENTIFIER=${SCRIPT_NAME}"

# Function to log a message with custom fields
log_message() {
  local message=$1
  logger --tag="${SCRIPT_NAME}" --journald <<EOF
$CUSTOM_FIELDS
MESSAGE=$message
EOF
}

log_message "LOG ALL THE THINGS!"
```

If we follow the logs with `journalctl -f` then we see our message logged:

```
Aug 01 09:45:14 archlinux journald-logging-example.sh[211637]: LOG ALL THE THINGS!
```

If we follow the logs to output json with `journalctl -f  --output=json-pretty` we see more of the structured logging:

```
{
    "MESSAGE" : "LOG ALL THE THINGS!",
    "__CURSOR" : "s=fa06f4c5a037464b96005ed4ce7f52a8;i=f5c7;b=04ca4289f89e4cacb7cee8c1ff745a5d;m=ad6fc295b;t=61ea0422ea2d2;x=e547b33cab1ee776",
    "__MONOTONIC_TIMESTAMP" : "46556522843",
    "_GID" : "1000",
    "__SEQNUM_ID" : "fa06f4c5a037464b96005ed4ce7f52a8",
    "LOGGER" : "journald-logging-example.sh",
    "CATEGORY" : "blog",
    "_PID" : "211637",
    "TAG" : "demo",
    "SYSLOG_IDENTIFIER" : "journald-logging-example.sh",
    "_MACHINE_ID" : "73841285dab34fa7aaebb633b7cb6f62",
    "__SEQNUM" : "62919",
    "_BOOT_ID" : "04ca4289f89e4cacb7cee8c1ff745a5d",
    "_RUNTIME_SCOPE" : "system",
    "_TRANSPORT" : "journal",
    "_SOURCE_REALTIME_TIMESTAMP" : "1722523514217132",
    "__REALTIME_TIMESTAMP" : "1722523514217170",
    "_UID" : "1000",
    "_COMM" : "logger",
    "_HOSTNAME" : "archlinux"
}
```

These custom fields allow us to tag various scripts and then filter logs based on those. So if we wanted to see all logs with the TAG `demo`, we can show those using

```
journalctl -f TAG=demo
```

## What if we do less?

If we do just the bare minimum to log from our bash script then we get a lot less data. Here is the bare minimum that you can do to log from bash:

```bash
logger "LOG some of THE THINGS!"
```

You'll notice that with `journalctl -f`` the log line is now coming from my user and not being identified by the bash script that it is coming from.

```
Aug 01 09:55:27 archlinux mike[214238]: LOG some of THE THINGS!
```

If we look at the structured log then we see no custom fields for easy filtering:

```
{
    "__REALTIME_TIMESTAMP" : "1722524127356578",
    "SYSLOG_FACILITY" : "1",
    "_RUNTIME_SCOPE" : "system",
    "SYSLOG_TIMESTAMP" : "Aug  1 09:55:27 ",
    "_BOOT_ID" : "04ca4289f89e4cacb7cee8c1ff745a5d",
    "__SEQNUM_ID" : "fa06f4c5a037464b96005ed4ce7f52a8",
    "_MACHINE_ID" : "73841285dab34fa7aaebb633b7cb6f62",
    "_UID" : "1000",
    "_PID" : "214238",
    "_HOSTNAME" : "archlinux",
    "__CURSOR" : "s=fa06f4c5a037464b96005ed4ce7f52a8;i=f5ca;b=04ca4289f89e4cacb7cee8c1ff745a5d;m=afb87ed2b;t=61ea066ba66a2;x=d76a9719c2721e55",
    "SYSLOG_IDENTIFIER" : "mike",
    "__MONOTONIC_TIMESTAMP" : "47169662251",
    "MESSAGE" : "LOG some of THE THINGS!",
    "PRIORITY" : "5",
    "_GID" : "1000",
    "_SOURCE_REALTIME_TIMESTAMP" : "1722524127356478",
    "_TRANSPORT" : "syslog",
    "__SEQNUM" : "62922",
    "_COMM" : "logger"
}
```
