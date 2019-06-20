---
title: "Network Protocals"
date: 2019-06-19T09:00:58Z
categories: ["network"]
draft: false
---

# Table of Contents
1. [TCP](#tcp-transmission-control-protocal)
2. [UDP](#udp-user-datagram-protocal)

#### TCP (Transmission Control Protocal)
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
---
<br>
#### UDP(User Datagram Protocal)
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

* SSH (port# 22)
    * protocal - SSH (its a communication protocal just like http, https, ftp...etc)
    * SSH is client(/usr/bin/ssh)
    * SSHD is server(openssh-server)
        ``` 
        -- Install openssh-server
        $ sudo apt-get install openssh-server
        
        -- sshd (ssh daemon server)
        $ systemctl start ssh
        ```
    * Authenticatoin methods(ssh user@192.168.56.101)
        * password
        * Public & Private key
            * ssh-keygen to generate ssh public & private keys
            * ~/.ssh/id_rsa     (Private Key)
            * ~/.ssh/id_rsa.pub (public Key)
            * public key goes into "authorized_keys" file
            
            ``` 
             $cat ~/.ssh/authorized_keys
              ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQC6rsvFUW/CD3x/HLp/6WJKPFwqMqex5LnEvMsQvrPtOs4rarQs4JZqwfBOhGpBB3MGU8OfDvBYjL2JMOyw/YqNtbhnSH2n5/Sco5Sge11SJuy1HbjrkVJE/fyZqxzyypsI8/7HqOYRxArCHHdg56Oz0MAZfeTLNIkvvL7CDyoc5snoiCWrLaQnDmOkKArrdVq6VoABWUFHfEN3/AERh6SOfwSHl5y/7uvcW7Yaemv6mm1MnEqCqi/Wo8ratQ9WFEvm2md8a4Hk4gD+VVyqNTr/P8dAnLqCYY9XpAczHAOp9NFqAeTo9LhLOXfm7/d89kB5ZIbobiuo6GfdOR9Nb0EpRsN8Pr3MYYFxj06N0+FoQJjL/1BNnvjrbSS4BA7KX/Z3c08lcpxPUc7QoAuS8qkEIJyhPtVc4jtEBT7CkyKvi3UVFFLRawSbAwjrLYxdL1HwXCcpTw3iw0QAK5CYPklXphikiPTPy7JnvkxE9hH3/ALioWD8LG4rwYWf24iT+yM= INTEL@DESKTOP-G5I1PT9
            ```
            * Refer : ssh-add command
        * host based

* telnet (port# 23)
    ``` 
    -- Verify whether given port is open on a host
    $ telnet [host [port]]
    rchari:~$ telnet techtaste.me 443
    Trying 185.199.111.153...
    Connected to techtaste.me.
    Escape character is '^]'.
    
    ^]
    Connection closed by foreign host.
    ```

* DNS resolution (Port# 53)
    * DNS uses TCP for Zone transfer and UDP for name queries either regular (primary) or reverse
    * Host to IP(Forward lookup)
        * Client sends dns query to ISP(Resolver) 
        * ISP asks ROOT Server(top DNS) & ROOT server redirects to ISP to TLD(Top level Domain Server)
        
            ```     
            Note: TLD(Top level domain server) contains address of top level domains like .com, .net, .org.. etc.
            ```
        * TLD redirects ISP to authoritative name servers(ns1.yahoo.xxx)
        * ISP gets ip of the host from name server(ns1.yahoo.xxx) & ISP caches the ip.
        * ISP sends the ip of the domain to client(browser)
    * IP to Host(reverse lookup)
        * using nslookup"
    * protocal - uses either UDP or TCP
        ```
        A client computer will always send a DNS Query using UDP Protocol over Port 53. If a client computer does not get response from a DNS Server, it must re-transmit the DNS Query using the TCP after 3-5 seconds of interval. 
        ```
* FTP [Uses **two ports# 21(for command) & 20(for data transfer)**]

