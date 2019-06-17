---
title: "Go Format Output"
date: 2019-06-17T11:30:18Z
categories: ["Golang"]
draft: false
---

#### **Printing the verbs**
* General
    ```
    %v	the value in a default format
    	when printing structs, the plus flag (%+v) adds field names
    %#v	a Go-syntax representation of the value
    %T	a Go-syntax representation of the type of the value
    %%	a literal percent sign; consumes no value
    ```
    ---

    ``` go
    // Examples
    
    package main

    import (
    	"fmt"
    )
    
    type rect struct {
    	height float64
    	width float64
    }
    
    func main() {
    	r := rect{height : 12, width: 15}
    	fmt.Println(r)
    	fmt.Printf("%v\n", r)
    	fmt.Printf("For #v : %#v\n", r)
    	fmt.Printf("For +v : %+v\n", r)
    	fmt.Printf("%T \n", r)
    	
    	// Prints pecentage sign
    	fmt.Printf("%% \n")
    }
    
    
    -- Output --
    $ go run .\test\main.go
    {12 15}
    {12 15}
    For #v : main.rect{height:12, width:15}
    For +v : {height:12 width:15}
    main.rect
    %
    ```