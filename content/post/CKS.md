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


## Certificates
Check .csr certs information
``` bash
openssl req -text -noout -verify -in CSR.csr
```

## SSH
``` bash
adduser username [enter password on the prompt]

# Add user to sudo
visudo
raghav ALL=(ALL:ALL) ALL

# Allow passwordless sudo execution
raghav ALL=(ALL) NOPASSWD:ALL

# Modify user group
usermod <user> -G admin

# List members of a group
groupmems -g <group> -l

# SSH config file 
cat /etc/ssh/sshd_config

# Copy public key to remote host
ssh-copy-id -i ~/.ssh/id_rsa.pub raghav@hostname
```