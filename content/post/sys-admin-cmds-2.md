---
title: "Sys Admin Cmds 2"
date: 2019-06-12T01:22:21Z
categories: ["system admin cmds"]
draft: false
---

#### display inode details for a file 
``` 
$ stat <file>
```
---

``` 
$ stat /etc/passwd

--- Output ---
File: `/etc/passwd'
  Size: 2026            Blocks: 8          IO Block: 4096   regular file
Device: 811h/2065d      Inode: 752010      Links: 1
Access: (0644/-rw-r--r--)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2007-08-20 23:19:20.000000000 +0530
Modify: 2007-07-07 00:06:56.000000000 +0530
Change: 2007-07-07 00:06:56.000000000 +0530
```

#### Create a user & group

``` 
--- create a user & group
$ sudo useradd -m testuser

--- set passwd for the user
$ sudo passwd testuser


--- create a group
sudo groupadd <groupname>
$ sudo groupadd testgroup

```

#### Adding user to a group
``` 
sudo usermod -a -G <group> <user>
$ sudo usermod -a -G testgroup testuser
```

#### list users for a given group
``` 
$ grep <username> /etc/group
$ grep testuser /etc/group

```
#### User passwords
``` 
User encrypted passwords are stored in /etc/shadow.

$ cat /etc/shadow

Note: This file contains passwords of users with second field 'x' only in /etc/passwd 
```

#### Delete user or group
``` 
$ sudo userdel testuser
Note: above cmd deletes the primary group 'testuser' of user 'testuser'
 
$sudo groupdel <groupname>
```

#### Chown cmd
``` 
$ chown <new_user>:<new_group> <filename>

$ chown testuser:testgroup example.txt


 This command picks group of the specified user.
$ chown <user>: <file>


$ chown :<Group> <file>
```


#### Recursively change ownership
``` 
$ chown -R USER:GROUP DIRECTORY

$ chown -R testuser: /var/www
```


#### Chmod

``` 
chmod [reference][operator][mode] <file>
 

 
7 = rwx
6 = rw-
5 = r-x
4 = r--
3 = -wx
2 = -w-
1 = --x
0 = ---


$ chmod g+rw <file>
$ chmod a=r <file>


Note: 
 
[reference] can be one of
u - user
g - group
o - other
a - all

[operator]
 +  - append permissions
 -  - remove permissions
 =  - match exact permissions
 
[mode]
r  - read
w  - write
x  - execute
```


