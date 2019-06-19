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
    * Its Dominant protocal & Used for
        * Web (http and https)
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

        
* HTTP                  
    * verion : HTTP/1.x (aka H1)
        * Features
            * Contents of each stream are HTTP 1.1 requests and responses
            * Single persistent connection(TCP)
            * Semantics like HTTP methods, HTTP Headers & Response Status Codes
            
        * Flaws
            * No Server Push; Low performance
            * Messages are not converted to binary format
    
    * version : HTTP/2.0 (aka H2)
        * Features
            * Server push
            * Compression of request headers
            * Multiplexing
            * Supports Single TLS encrypted(With use of SSL cert)            
            * The conversion of messages into binary allows HTTP/2 to try new approaches to data delivery not available in HTTP/1.
            
            * Stream concurrency: Carrying multiple streams over a single TCP connection
            * Flow Control: receiver signals the sender for the maximal amount of data it is allowed to transmit (over a stream/TCP connection)
            * Stream priority: Sender signals the receiver for the priority of this stream, compared to others
            * Stream dependency: Sender signals the receiver on recommended order for processing the streams
            
            
* HTTPS(SSL/TLS)
                
* Ping
    * protocal -  Internet Control Message Protocol (ICMP)
    
        ```
        It uses ICMP. 
        To be more precise ICMP type 8 (echo message) and type 0 (echo reply message) are used. ICMP has no ports! 
        ```
    * port - Does not use TCP or UDP. 

* SSH
    * protocal - SSH
    * port - 22
    * Encryption -


* ftp
* telnet
* smtp

* gRPC
    * protocal -
    * port - 

* DNS resolution
    * protocal -
    * port - 
