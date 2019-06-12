---
title: "Sys Admin Cmds 3"
date: 2019-06-12T15:53:19Z
categories: ["system admin cmds"]
draft: false
---

#### extend volume

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
