---
title: "Go Synchronization"
date: 2019-07-16T02:24:33Z
categories: ["golang"]
draft: false
---

#### **sync.Mutex*
``` go          
    m := sync.Mutex
    
    m.Lock() // for locking
    m.Unlock() // for unlocking
```

#### **sync.RWMutex**
``` go 
    m := sync.RWMutex
    
    // Read lock & Read unlock.
    m.RLock()
    m.RUnlock()
    
    // for Write locks & write unlocks
    m.Lock()
    m.Unlock()
```

#### **sync.WaitGroup**
``` go 
e.g.

func main() {
    var wg sync.WaitGroup
    
    wg.Add(1)
    go func() {
        fmt.Println("Inside my goroutine")
        wg.Done()
    }()
    wg.Wait()

    fmt.Println("Finished Execution") 
}
```
