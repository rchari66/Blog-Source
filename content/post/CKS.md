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


## Systemctl
``` bash
Find out the name of the unit file:
systemctl list-units --all | grep nginx

Stop Nginx service:
systemctl stop nginx

Find out the location of the service unit:
systemctl status nginx

Remove the unit file:
rm /lib/systemd/system/nginx.service
```

## ufw (uncomplicated firewall)
``` bash
# Run the commands: 
ufw allow from 135.22.65.0/24 to any port 9090 proto tcp 

ufw allow from 135.22.65.0/24 to any port 9091 proto tcp on node01
# To enable the firewall: 
ufw enable
```