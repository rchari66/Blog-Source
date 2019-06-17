---
title: "Go Basics"
date: 2019-06-17T06:49:18Z
categories: ["Golang"]
draft: false
---

#### command line args
-- main.go
``` go
package main

import (
    "os"
    "fmt"
)
func main() {
    argsWithProgramName := os.Args
    argsWithoutProgramName := os.Args[1:]
    
    fmt.Println(argsWithProg)
    fmt.Println(argsWithoutProg)
}
```
```
-- OUTPUT --
PS C:\Users\INTEL\Desktop\golang> go run .\main.go "a b c" "sdf"
[C:\Users\INTEL\AppData\Local\Temp\go-build928898898\b001\exe\main.exe a b c sdf]
[a b c sdf]
```
---

#### **Reading Files**
``` go
package main

import (
    "os"
    "fmt"
    "bufio"
    "log"
)

func main() { 

    f, err := os.Open("logfile.log")
    
    if err != nil {
        log.Fatal("Unable to open log file")
    }
    
    defer f.Close()
    
    r := bufio.NewReader(f)
    
    for {
        str, err := r.ReadString('\n')
        
        if err != nil {
            break
        }
        
        fmt.Println(str)
    }

}
```