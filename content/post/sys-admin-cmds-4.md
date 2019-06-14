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

* Jmap : it prints heap dumps into a specified file location
    ``` 
    -- This used for heap dump; It is included in JDK /bin
    $ jmap -dump:format=b,file=<file-path> <pid>
    
    $ jmap -dump:format=b,file=/tmp/dumpoutput.bin 2034 
    ```
* HeapDumpOnOutOfMemoryError
    ``` 
    -- By passing the arguments "-XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/opt/tmp/heapdump.bin" to Java startup application.
    
    Note: Best Practice: Keep this property configured in all the applications at all the times, as you never know when OutOfMemoryError will happen.
    ```
* Jcmd
    ```
    $ jcmd <pid> GC.heapdump <outputfile>
    $ jcmd 1240 GC.heap_dump /tmp/heapdump.bin
    ```
* UI based tools for taking heapdump
    ``` 
    -- JvisualVM
    -- JMX

#### Create systemd service
* Example .service file for systemd
    ``` 
    [Unit]
    Description=A sample service
    After=network.target
    After=systemd-user-sessions.service
    After=network-online.target
    
    [Service]
    User=testuser
    Type=forking
    ExecStart=/home/testuser/start-sample-service.sh
    ExecStop=/home/testuser/stop-sample-service.sh
    TimeoutSec=30
    Restart=on-failure
    RestartSec=30
    StartLimitInterval=350
    StartLimitBurst=10
    
    [Install]
    WantedBy=multi-user.target
    ```
    ``` 
    Note: The location of this .service file should be 
    /etc/systemd/system/sample.service

    "/etc/systemd/system/" contains all the .service files for systemd
    ```
* Enable the service to run at system startup
    ```
    $ systemctl enable sample.service
    ```