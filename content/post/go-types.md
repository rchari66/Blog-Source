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
    
    ``` go
    // Structs can be initialized in two ways.
    -- Using dot notation
    
    p := Point{}
    p.X = 1
    p.Y = 2
    
    -- Using struct literal
    
    p := Point{X:1, Y:2}\
    
    ```

* Initializing(using **new** keyword)
    ``` go
    x := new(int) // x value is = 0
    
    ```
    Note: Go uses **new** expression to allocate a zeroed value of the requested type and to return a pointer to it

* Initializing(using **make** keyword)
    ``` go
    -- make is used to initialize slices, maps & channels
    ```

* Arrays

    ``` go
    // The type [n]T is an array of n values of type T
    var arr [10]int
    var names [20]string
    
    // Set array entries at the time of declaration
    arr := [5]int{1,2,3,4,5}    // len(a) will be 5
    arr := [...]int{1,2,3,4,5}  // len(a) will be 5; using ellipsis(...)
    
    names := [2]string{"Hello", "World"}
    names := [...]string{"Hello", "World"} // using ellipsis(...)
    ```
    ``` go
    // Printing arrays
    a := [...]string{"Hello", "World!"}
    
    fmt.Println(a)
  	// [hello world!]
  	fmt.Printf("%s\n", a)
  	// [hello world!]
  	fmt.Printf("%q\n", a)
  	// ["hello" "world!"]
    ```
    ``` go
    // Multidimentional arrays.
    var a [2][3]string
    var arr [5][5]int
    ```

* Slices([]T is a slice with elements of type T)
    ``` go
    // Slices wrap arrays to give a more general, powerful, and convenient interface to sequences of data
    
    p := []int{2, 3, 5, 7, 11, 13} // slice literal
    
    s := make([]string, 5) // slice of size 5;
    
    s[0] = "Hello"
    
    // To increase size of the slice
    s = append(s, "New string")
    
    
    // append another slice
    cities := []string{"San Diego", "Mountain View"}
  	otherCities := []string{"Santa Monica", "Venice"}
  	cities = append(cities, otherCities...)
  	
  	// nil slices
  	var s []int
  	
  	if s == nil {
  	  fmt.Println("s is nil")
  	}
    -- Output --
    s is nil
    
    
    // --Range over slices
    var pow = []int{1, 2, 4, 8, 16, 32, 64, 128}
    
    func main() {
        for i, v := range pow {
            fmt.Printf("2**%d = %d\n", i, v)
        }
    }
    
    -- Output --
    2**0 = 1
    2**1 = 2
    2**2 = 4
    2**3 = 8
    2**4 = 16
    2**5 = 32
    2**6 = 64
    2**7 = 128
    
    // -- Range over map
    cities := map[string]int{
  		"BLR":    1234,
  		"HYD": 5678
  	}
  	for key, value := range cities {
  		fmt.Printf("%s has pincode : %d\n", key, value)
  	}
  	
  	-- Output --
  	BLR has pincode : 1234
  	HYD has pincode : 5678
  	
    ```

* Maps
    ``` go
    // -- Declaration
    m := map[string]int {
      "a" : 1,
      "b" : 2
    }
    fmt.Printf("%#v \n", m)
    fmt.Println(m)
    -- Output --
    map[string]int{"a":1, "b":2}
    map[a:1, b:2]
    
    // -- Manipulating maps
    -- insert or update
    m[key] = value
    
    -- retrieve
    v = m[key]
    
    -- delete
    delete(m, key)
    
    -- check for key with two-assignment variables
    v, ok = m[key]
    
    ```