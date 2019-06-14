---
title: "Web Server vs App Server"
date: 2019-06-14T12:04:21Z
categories: ["Servers"]
draft: false
---



### Web Server vs Applicatoin Server
    Web Server is designed to serve HTTP Content. App Server can also serve HTTP Content but is not limited to just HTTP. 
    It can be provided other protocol support such as RMI/RPC
---

#### Web Server
* Servers only web pages. Could be static or Dynamic pages
    * Static Pages
        * HTML
        * CSS
        * JavaScript(Interactively)
    * Dynamic Pages
        * JSP, Servlet (JAVA + HTML + CSS + JavaScript)
        * PHP (PHP + HTML + CSS + JavaScript)
        * ASP.NET (C# + HTML + CSS + JavaScript)

#### Applicatoin Server
    Most of the application servers have Web Server as integral part of them, that means App Server can do whatever Web Server is capable of. 
    Additionally App Server have components and features to support Application level services such as Connection Pooling, 
    Object Pooling, Transaction Support, Messaging services etc
    
* Enterprise Java Bean(EJB)
* Oracle WebLogic
* Glassfish
* JBoss