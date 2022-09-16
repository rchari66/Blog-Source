---
title: "CKS"
date: 2022-09-14T05:02:26Z
categories: ["K8S"]
draft: false
---

// TODO: Refer mkDoks

## SSH security

## Restrict Kernal modules


## Open Ports & Listening ports
``` bash
netstat -an | grep -w LISTEN
```
## Check ports are used by which services
``` bash
cat /etc/services | grep -w 53
```

## List processes and thier ports
``` bash
netstat -natp 
netstat -natp | grep "9090"
```

