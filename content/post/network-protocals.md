---
title: "Network Protocals"
date: 2019-06-19T09:00:58Z
categories: ["network"]
draft: false
---

#### **In Progress..**
* TCP(Transmission Control Protocal)
    * Description :
    
        ``` 
        TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network
        ```
    * Its a persistent connection
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

        ![TCP vs IDP](https://techtaste.me/img/tcp-udp.png)
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
    
    * version : HTTP/2.0 (aka H2; supports only with SSL/TLS)
        * Features
            * Protocol negotiation mechanism — protocol electing, eg. HTTP/1.1, HTTP/2 or other.
            * Server push
            * Compression of request headers(Using HPACK)
            * Multiplexing over a single TCP connection
            * Binary protocal
            * Stream concurrency: Carrying multiple streams over a single TCP connection
            * Flow Control: receiver signals the sender for the maximal amount of data it is allowed to transmit (over a stream/TCP connection)
            * Stream priority: Sender signals the receiver for the priority of this stream, compared to others
            * Stream dependency: Sender signals the receiver on recommended order for processing the streams
            
        e.g.
        ![HTTP/1.0 vs HTTP/2.0](https://techtaste.me/img/http1-http2.png)
        e.g.
        ![HTTP/1.0 vs HTTP/2.0](https://techtaste.me/img/http1-http2-2.png)
    * Ref : https://medium.com/@factoryhr/http-2-the-difference-between-http-1-1-benefits-and-how-to-use-it-38094fa0e95b

* HTTPS(SSL/TLS)
    * Works on HTTP protocal with encrypted TLS/SSL connection
        * Browser requests https cert & gets certficate & signature of the ssl cert.
        * Browser verifies the cert's integrity & identity
        * Browser creates a symetric key, encrypts it usnig server's public key and sends to server.
        * Both Browser & Server uses this symetric key to encrypt the messages.
        
    * Some of SSL cert types
        * Domain Validation SSL
        * Wildcard SSL 
        * Multidomain SLL certs 
    Note: All browsers enforce SSL certs to be used with HTTP/2.0 protocal.
    * 
    

* Ping
    * protocal -  Internet Control Message Protocol (ICMP)
    * Sends echo request packet to an address, then waits for a reply.
    * The ping is successful only if:
        - the echo request gets to the destination, and
        - the destination is able to get an echo reply back to the source within a predetermined time called a timeout.
        ```
        To be more precise ICMP type 8 (echo message) and type 0 (echo reply message) are used. ICMP has no ports!
        ```
    * port - No Ports. Does not use TCP or UDP. 

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
