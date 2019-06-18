---
title: "Go Types"
date: 2019-06-17T16:55:16Z
categories: ["Golang"]
draft: false
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
    v, ok := variable.(<type>)
    
    -- 
   type Counter struct {
    	count int
    }
    
    func printString(value interface{}) {
    	switch str := value.(type) {
    	case string:
    		fmt.Println(str)
    	case Counter:
    		fmt.Println(str.count)
    	}
    }
    
    func main() {
    	c := Counter{count: 10}
    	var str string = "Hello world"
    
    	printString(c)
    	printString(str)
    }
    ```
    ``` go
    // checking if an error is of a certain type:
    if err != nil {
      if msqlerr, ok := err.(*mysql.MySQLError); ok && msqlerr.Number == 1062 {
        log.Println("We got a MySQL duplicate :(")
      } else {
        return err
      }
    }
    ```
* Structs
    ``` go
    type Point struct {
    	X, Y int
    }
    
    var (
    	p = Point{1, 2}  // has type Point
    	q = &Point{1, 2} // has type *Point
    	r = Point{X: 1}  // Y:0 is implicit
    	s = Point{}      // X:0 and Y:0
    )
    ```

* Initializing(using **new** keyword)
    ``` go
    x := new(int) // x value is = 0
    
    ```
* Initializing(using **make** keyword)
    ``` go
    -- make is used to initialize slices, maps & channels
    ```