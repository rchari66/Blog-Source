---
title: "Go Types"
date: 2019-06-17T16:55:16Z
categories: ["Golang"]
draft: true
---

#### **Types**
* Built-in types
    ``` go
    bool 
    string
    
    Numeric:
    int (either 32 or 64bit)
    uint (either 32 or 64 bit)
    
    uint8, uint16, uint32, uint64 (all Unsigned 8, 16, 32, 64 bit integers respectively)
    int8, init16, int32 ,int64 (signed integers)
    
    float32
    float64
    ```
* Type conversions; T(v) converts value v to T type.
    ``` go
    a := 10
    b := float64(a)
    var u uint = uint(b)
    ```
* Type Assertion
    
    Type assertion takes a value and tries to create another version in the specified explicit type.
    ``` go
        as
    ```