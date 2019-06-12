---
title: "Process(ps) cmd in linux"
date: 2019-06-11T16:51:00Z
categories: ["Basic Linux CMDs 1", "Debug"]
draft: false
---

#### fork vs exec

> fork creates child process and returns child's pid

> child process gets zero as returned value from fork.

#### list by user
``` bash
$ ps -u $USER
```

Ref:  https://fedoramagazine.org/inspect-manage-processes-ps/

#### list processes by group
``` bash

$ ps -G groupname1 groupname2
e.g.
$ ps -G root
```

#### Inverse selection (Using **-N** option)
> Select all the process those not started by root(group);

``` 
$ ps -u root -N
```
---

Note: htop or top to see how much cpu, ram used for the processes

---
#### Process states
* RUNNING
* WAITING
* STOPPED
* ZOMBIE


#### Process filters
``` 
ps -C firefox -L -o pid,tid,pcpu,state,nlwp,cmd 

```

#### Sort output
``` 
$ ps -eF --sort -rss
```

#### process tree
``` 
--- display process tree of current user processes
$ ps f


-- display process tree of all user processes
$ ps -e f
```
Note: **htop** can be used to view process tree as well.