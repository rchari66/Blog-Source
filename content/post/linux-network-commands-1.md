---
title: "Linux network commands 1"
date: 2019-05-18T05:30:33Z
categories: ["network cmds 1"]
draft: false
---

## Ifconfig
``` language
    Used to configure network interface parameters. 
    Checking ip of the machine.
```
    
## traceroute
``` language
Print the route packets take to network host.
```

## dig(Domain information groper)
``` language
Dig (domain information groper) query DNS related information like A Record, CNAME, MX Record etc
```

## telnet
``` language
Connects to host on given port using telnet protocal. 
If connection successful then host is working fine.
```

## nslookup
``` language
It queries internet domain name servers.
```
<details><summary>Options</summary>
<p>

    > use with -r option to display route table information.

</P>
</details>

## netstat
``` language
Displays each of network connections and open sockets.
```

## ip
``` language
$ ip addr show 
```

## iptables ( blocks or allows traffic on a Linux host )
``` language
$ sudo iptables -S
-P INPUT DROP
-P FORWARD DROP
-P OUTPUT DROP
-A INPUT -p tcp -m tcp --dport 22 -j ACCEPT
-A INPUT -i eth0 -p udp -m udp --sport 53 -j ACCEPT
```
sudo iptables -S

## scp
``` language
To copy files remotely.
```

## w
``` language
w prints a summary of the current activity on the system, 
including what each user is doing, and their processes.
```

## nmap
``` language
Checks all open ports on given server.
Its a powerful tool.
```

## ping
``` language
pings given host to check the connection.
```