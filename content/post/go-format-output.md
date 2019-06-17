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
* Boolean
    ``` go
    func main() {
    flag := true
	
	fmt.Println(flag)
	
	fmt.Print("Boolean value of flag : ", flag,  "\n")
	
	fmt.Printf("Boolean value of flag : %t \n", flag)
	}
	
	-- Output --
	true
    Boolean value of flag : true
    Boolean value of flag : true
    ```
 * Integer & Float   
    ``` go
    -- Integer
    %b	base 2
    %c	for char
    %d	base 10(for integer)
    %o	base 8(octa)
    %q	a single-quoted character literal safely escaped with Go syntax.
    %x	base 16, with lower-case letters for a-f
    %X	base 16, with upper-case letters for A-F
    %U	Unicode format: U+1234; same as "U+%04X"
    
    -- Examples
    a := 4
    
    fmt.Printf("Binary: %b\n", a)
    
    fmt.Printf("Decimal : %d\n", a)
    
    fmt.Printf("Hexa : %x\n", a)
    
    fmt.Printf("Hexa : %X\n", a)
    
    -- Output --
    Binary: 100
    Decimal : 4
    Hexa : 4
    Hexa : 4
    
    
    -- Float --
    f := 10000.800
    fmt.Pritnf("10.2%f") // fit the float in 10 characters
    
    -- Output --
          10000.80
    ```

* Strings & Slices
    ``` go
    -- String and slice of bytes
    %s - string
    %q - quoted string
    
    -- Example
    str := "Hello World!"
    fmt.printf("%s \n", str)
    fmt.printf("%q \n", str)
    
    -- Output --
    Hello World!
    "Hello World!"
    ``` 
    ---
    ```
    -- Pointer
    %p	base 16 notation, with leading 0x
    
    a := 10
    fmt.Printf("Pointer of a : %p \n", &a)
    
    -- Output --
    Pointer of a : 0xc000064090
    ```
    Note: %v can be used for any of the below types.
    - int, float, bool, uint, uint8, string,
    - chan, float32, pointer

* Other complex Objects
    ``` go
    Complext objects will be printed like this..
    
    struct:             {field0 field1 ...}
    array, slice:       [elem0 elem1 ...]
    maps:               map[key1:value1 key2:value2 ...]
    pointer to above:   &{}, &[], &map[]
    ```
    Ref: https://golang.org/pkg/fmt to know more on 
    - Scan, Scanf, Scanln, Fscan, Fscanf, Fscanln for **Scanning**
    - Sprint, Sprintf, Sprintln for create and return **strings**

    