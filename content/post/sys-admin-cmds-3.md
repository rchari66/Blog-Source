---
title: "Sys Admin Cmds 3"
date: 2019-06-12T15:53:19Z
categories: ["system admin cmds"]
draft: false
---

TODO : extend existing volumes

---

#### mount
``` 
$ mount <source> <dest>

$ mount /dev/sda2 mountDestDir

--- list all mount points
$ mount -l

--- list all mount points of given type.
$ mount -l -t <type>

```

#### find
``` 
-- find by name
$ find -name <name>

-- find not matching name

$ find -not -name <name-to-avoid>

-- find by type
$ find / -type <type> <name>

<type> could be one of
f = file
d = directory
l = symbolic link
c = character devices
b = block devices

e.g.
$ find / -type f -name "*.html"
```

#### Find by size
``` 
c: bytes
k: Kilobytes
M: Megabytes
G: Gigabytes
b: 512-byte blocks

-- find exactly 100 bytes file/directories
$ find / -size 100c

-- find less than 50Mb files in current directory
$ find -size -50M

-- all files more than 1Gb
$ find -size +1G
```

#### Find by Time
``` 
Access Time: Last time a file was read or written to.
Modification Time: Last time the contents of the file were modified.
Change Time: Last time the file's inode meta-data was changed.

-- find files accessed less than two days
$ find / -atime -2

-- find files whose permissoins changes in last one day.
$ find / -ctime -1

-- find files modified in last two minutes
$ find / -mmin -2

** find can also used to compare with another file
$ find -newer <file-reference>

```

#### Finding by Owner and permissoins
``` 
-- find files owned by given user
$ find / -user <user>

-- owner
$ find / -group <group>

---- find by permissions
$ find / -perm 400

$ find -perm 777
```

#### Find by depth
``` 
-- find by max depth of 2; means search only two sub-directory levels.
$ find -maxdepth 2 -name <name>

-- find by min depth 3
$ find -mindepth 3 -name <name>
```

#### Finding and executing commands on those files.
``` 
-- find by permissions and change owner to different user.
$ find -perm 755 -exec chown <user>: {}\;
e.g.
$ find . -type f -perm 644 -exec chmod 664 {} \;


Note:   The "{}" is used as a placeholder for the files that find matches. 
        The "\;" is used so that find knows where the command ends.
```

#### Combine results using -and/-or
``` 
$ find -name file1 -or -name file2

$ find -name file1 -and -perm 600
```