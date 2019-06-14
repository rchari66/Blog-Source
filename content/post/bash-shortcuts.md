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

#### Substitute a word in last command and execute it.
``` 
$ echo Hello World!
Hello World!

$ ^Hello^New Hello
echo New Hello World!
New Hello World!


Note: This is equilent to below command
!!:s/Hello/New Hello/
$ !!:s/New Hello/Hello
echo Hello World!
Hello World!
$
```

#### Execute/view nth command from history
``` 
-- show & execute 190th command
$ !190

-- only show 190th command
$ !190:p
```

#### View last 10 commands from history
``` 
$ history 10
```

#### Execute last 5th command from history
``` 
$ !-5

-- only view last 5th command
$ !-5:p
```

#### Repeat entire command line
``` 
$ echo Hello World! !#
Hello World! echo Hello World!

-- Repeat only 2nd keyword
$ echo Hello World! !#:2
Hello World! World!
```


