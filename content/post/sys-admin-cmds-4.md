---
title: "Sys Admin Cmds 4"
date: 2019-06-12T17:57:21Z
categories: ["system admin cmds"]
draft: false
---

#### Run levels are
    Run level 0 is matched by poweroff.target (and runlevel0.target is a symbolic link to poweroff.target).
    Run level 1 is matched by rescue.target (and runlevel1.target is a symbolic link to rescue.target).
    Run level 3 is emulated by multi-user.target (and runlevel3.target is a symbolic link to multi-user.target).
    Run level 5 is emulated by graphical.target (and runlevel5.target is a symbolic link to graphical.target).
    Run level 6 is emulated by reboot.target (and runlevel6.target is a symbolic link to reboot.target).
    Emergency is matched by emergency.target.

#### Java threaddump
``` 
-- If you have JDK, we can jstack command
$ jstack <ProcessID> > threaddump-file.txt

-- Most of the enterprises do not install JDK due to security reasons. In such cases they only JRE to run the java application.
    - find the id of java application
$ ps -e f | grep java
    - threaddump using below command
$ kill -3 <ProcessId>
```

#### Heap dump



#### Create systemd service