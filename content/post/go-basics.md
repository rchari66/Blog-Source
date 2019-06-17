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

#### **Executing commands in go**

``` go
// execute and return output
package main

import (
    "os/exec"
    "log"
    "fmt"
)

func main() {
    output, err := exec.Command("date").Output()
    
    if err != nil {
        log.Fatal("Failed to execute command" + err)
    }
    
    fmt.Println(output)
}
```

``` go
// start and wait for the command to exit
 
 func main() {
     cmd := exec.Cmd("sleep", "5")
     
     err := cmd.Start()
     if err != nil {
         log.Fatal(err)
     }
     
     fmt.Println("Waiting for the command")
     err := cmd.Wait()
     
     fmt.Printf("Command has been executed with error: %v", err)
     
 }
```

``` go
// Stdoutpipe
func main() {
    // tail from first line; and keep follow the file for any chagnes
    // tail -Fn+1 <filename>
    
    cmd := exec.Cmd("tail", "-Fn+1", "logfile.log")
    
    stdout, err := cmd.StdoutPipe()
    
    if err != nil {
        log.Fatal(err)
    }
    
    // start the command
    err = cmd.Start()
	if err != nil {
		log.Fatal(err)
	}

    // io.Reader object.
	r := bufio.NewReader(stdout)
	
	for {
	    line, error := r.ReadString("\n")
	    
	    if error != nil {
	        log.Fatal(error)
	    }
	    
	    fmt.Println(line)
	}
    
    // Wait for the command
    err = cmd.Wait()
    
    log.Printf("Command finished with error: %v", err)
    
}
```