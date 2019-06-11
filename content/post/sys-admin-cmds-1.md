---
title: "Sys Admin Cmds 1"
date: 2019-05-19T06:34:32Z
categories: ["system admin cmds 1"]
draft: false
---
## lscpu
``` language
list of cpus.
```

## lsmem
``` language
list of memory.
```

## lsof (list open files)
``` language
lsof -i tcp:80
```

## df (disk free space)
``` language
Display free disk space  

Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       32G  4.7G   26G  16% /
tmpfs           1.9G     0  1.9G   0% /dev/shm

```

## du (disk space usage)
``` language
 du - estimate file space usage
 du -sh /var/*
```
## id
``` language
$ id
uid=501(operations) gid=100(users) groups=100(users)
```

## curl
``` language
curl -I -s google.com

-I : Header information.
-s : silence body response.
-k : insecure
-v : verbose
-V : version
```
## ps
``` language
$ ps -ef 
$ ps -u <username> (display all user processes)
$ sudo ps aux
a = show processes for all users
u = display the process's user/owner
x = also show processes not attached to a terminal
```
## docker stats
``` language
$ docker stats <container-id>
CONTAINER ID        NAME                CPU %               MEM USAGE / LIMIT     MEM %               NET I/O             BLOCK I/O           PIDS
5e1485ac499f        zen_khayyam         0.17%               147.5MiB / 9.251GiB   1.56%               14.3MB / 18.4MB     113MB / 8.66MB      64
```
## basic comamnds
    > cat, ls, tail, env

## chmod 
``` language
chmod 400 shh_key.pem
```

## history (display history commands)
``` language
$ history 
   63  kubectl describe pv pvc-b3123e13-51e3-11e9-b709-124cac572d38 
   64  kubectl delete pv pvc-b3123e13-51e3-11e9-b709-124cac572d38 
   65  clear
   66  kubectl get pods
   67  kubectl get pods
   68  clear
   69  kubectl get pods
   70  kubectl get pods
   71  kubectl get ns
   72  kubectl get pod

```
