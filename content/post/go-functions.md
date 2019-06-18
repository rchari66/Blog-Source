---
title: "Go Functions"
date: 2019-06-17T16:08:53Z
categories: ["Golang"]
draft: true
---

#### **function declaration**
* Syntaxt

    ``` go
    func <nameOfTheFunction>(arg1 typ1, arg2 type2) <returnType> () {
        ...
    }
    ```
    e.g.
    ``` go
     func add(a int, b int) int {
         return a+b
     }
     
    -- Above function can be written as 
    func add(a, b int) int {
        
    }
    ```
    e.g.
    ``` go
     func location(city string) (state, country string) {
        ...
        ...
        return "BLR", "India"
     }
    ```
