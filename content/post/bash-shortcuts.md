---
title: "Bash Shortcuts"
date: 2019-06-14T09:20:00Z
categories: ["system admin cmds"]
draft: false
---

#### Show and execute most recent command
``` 
$ echo Hello World!
$ !!
echo Hello World!
Hello World!
```

#### Execute/View most recent command that starts with given key word
``` 
$ echo Hello World!

$ !echo
echo Hello World!
Hello World!

-- Only view the command(Do not execute)
$ !echo:p

Option ":p" only prints the command without executing it.
```

#### Arguments of last command can be referred using '!*'
``` 
$ echo Hello World!
Hello World
$ echo !*
echo Hello World!
Hello World!
```


#### First argument of last command can be referred by '!^'
``` 
$ echo Hello World!
Hello World
$ echo !^
echo Hello 
Hello
```

#### Last argument of last command can be referred by '!$'
``` 
$ echo Hello World!
Hello World
$ echo !$
echo World! 
World!
```
