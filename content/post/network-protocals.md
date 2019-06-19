---
title: "Network Protocals"
date: 2019-06-19T09:00:58Z
categories: ["new_post"]
draft: true
---

#### **In Progress..**
* TCP(Transmission Control Protocal)
    * Description :
    
        ``` 
        TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network
        ```
    * Three way handshare(at the begining)
        ```
        step1 : Client sends -> I want to talk -> Server
        step2 : Client recieves <- "Sure. Are you Ready? <- Server
        step3 : Client sends -> "Yes I am Ready" -> Server
        
            <- TCP Connection established ->
        ```
    * Its Dominant protocal
    * Used for
        * Web
        * Telnet
        * FTP
        * email
    
* UDP(User Datagram Protocal)
    * Description - provides a connectionless datagram service that emphasizes reduced latency over reliability. 
    * Sends Data to server; does not care whether it reached destination or not;
    * Its faster.

        ![TCP IDP](https://techtaste.me/img/Screenshot%20(4).png)
    * Used for 
        * Live streaming audio or video
        * DNS Queries, VoiceOverIP(VoIP),  Dynamic Host Configuration Protocol (DHCP)

* Ping
    * protocal -  Internet Control Message Protocol (ICMP)
    
        ```
        It uses ICMP. To be more precise ICMP type 8 (echo message) and type 0 (echo reply message) are used. ICMP has no ports! 
        ```
    * port - Does not use TCP or UDP. 

* SSH
    * protocal - SSH
    * port - 22
    * Encryption -

* nslookup
    * protocal -
    * port - 

* dig
    * protocal -
    * port - 

* telnet
    * protocal -
    * port - 

* http
    * protocal -
    * port - 

* https
    * protocal -
    * port - 
    
* gRPC
    * protocal -
    * port - 

* DNS resolution
    * protocal -
    * port - 

* SMPT

* 