---
title: "TCPDUMP cmd"
date: 2019-05-19T07:53:12Z
categories: ["network cmds"]
draft: false
---

## tcpdump -i any
``` language
To get the network packets from all network interfaces, run the following command,
```

## get packets on localhost with port 8288
``` language
tcpdump -i lo0 port 8288
```
## tcpdump -i eth0
``` language
get the network packets from a single interface
```

## tcpdump -i eth0 -w wirte_file_name
``` language
write all the captured packets to a file, use the ‘-w’ option,
```

## tcpdump -r packets_file
``` language
read an already created, old tcpdump file.
```

## tcpdump net 192.168.1.0/24
``` language
get packets from a whole netwrok
```

## tcpdump host 192.168.1.100
``` language
Get all the packets based on the IP address, whether source or destination or both
```

## tcpdump ssh
``` language
check all the packets used based on the protocol
```

## To get packets for a single port ot for a range of ports, use
``` language
$ tcpdump port 22
$ tcpdump portrange 22-8080
```

## More..
``` language
To get packets based on source or destination of an IP address, use

$ tcpdump src 192.168.1.100
$ tcpdump dst 192.168.1.100
$ tcpdump src 192.168.1.100 && port 22 -w ssh_packets
$ tcpdump port 443 or 80 -w http_packets
$ tcpdump -i eth0 src port not 22
```