---
title: "Python Basics"
date: 2019-07-02T07:23:07Z
categories: ["new_post"]
draft: false
---

#### **Open file and Display the whole content**
``` python
f = open("file.txt")
print(f.read())

Note: by default the opens in "r"(read) mode; Above code is same as below code

f = open("file.txt", "r")
print(f.read())
```

#### **Read first 5 bites of a file**
``` python
f = open("file.txt", "r")
print(f.read(5))
```

#### **Read 10 bites After first 100 bytes**
``` python
f = open("file.txt", "r")
print(f.tell())
f.seek(100)
print(f.tell())
print(f.read(10))
```

#### **List all files(recursively) for the directory**
``` python
#!/usr/bin/python
import subprocess, os
 
p = subprocess.Popen("find -type f", stdout=subprocess.PIPE, shell=True)
 
## Talk with date command i.e. read data from stdout and stderr. Store this info in tuple ##
## Interact with process: Send data to stdin. Read data from stdout and stderr, until end-of-file is reached.  ##
## Wait for process to terminate. The optional input argument should be a string to be sent to the child process, ##
## or None, if no data should be sent to the child.
(output, err) = p.communicate()
 
## Wait for process to terminate. Get return returncode ##
p_status = p.wait()
print("Command output : ", output.decode('utf-8'))

for file in output.decode('utf-8').split("\n"):
    if os.path.exists(file):
        print("file : {0}".format(file))


print ("Command exit status/return code : ", p_status)
```

#### **Slices**
Ref: https://docs.python.org/2.3/whatsnew/section-slices.html