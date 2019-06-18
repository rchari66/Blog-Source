---
title: "Go Variables Declaratoin"
date: 2019-06-17T14:44:35Z
categories: ["Golang"]
draft: true
---

#### **Variables declaration in go**
* Declaratoin
    ``` go
    var (
        name string
        age int
        city string
    )
    
    -- 
    var (
        name, city string
        age int
    )
    
    -- 
    var name string
    var city string
    var age int
    
    ```
* Initialization
    ``` go
    var (
        name string = "Chari"
        city string = "BLR"
        mobile int = 12345
    )
    -- Inferred typing
    var (
        name = "Chari"
        city = "BLR"
        mobile = 12345
    )
    --
    var (
        name, city, mobile = "Chari", "BLR", 12345
    )
    ```

* Short assignment "**:=**" (Inside a function only)
    ``` go
    func main() {
        name := "Chari"
        city := "BLR"
    }
    ```
* Function type
    ``` go
    var (
    	a = func() {
    		fmt.Println("a's function defination")
    	}
    )
    
    func main() {
    	a()
    }
    -- Output --
    a's function defination
    
    -- another e.g.
    func main() {
        a := func() {
            fmt.Println("a's function defination inside main function")
        }
    }
    ```

#### **Constants**
* define constants
    ``` go
    const (
        name = "Chari"
        fact = true
        Pi = 3.14
    )
    
    --
    const Pi = 3.14
    const fact = false
    ```

#### **Exported Variables**
* Name thats strts with capital is exported; Meaning it can be reffered from other packages.
    ``` go
    -- Below names Pi, ABC, Abc can be used in other packages.
    const Pi = 3.14
    var ABC string = "Foo string"
    var Abc string = "Abc"
    
    -- Below names name, city can not be accessed by other packages, but with in same package.
    var name string = "Chari"
    var city = "BLR"

    ```

#### **Pointers**
* declaration
    ``` go
    httpClient := &http.Client{}
    resp, err := httpClient.Get("http://github.com")
    
    Note: You can directly call methods, fileds on pointer without using *
    ```
* pass by value
    ``` go
    type Counter struct {
        count int
    }
    
    func increase(cnt Counter) int {
        cnt.counter++
        return cnt.counter
    }
    
    func main() {
        c := Counter{count:10}
        
        fmt.Println(increase(c))
        
        fmt.Println(c.count)
    }
    
    -- Output --
    11
    10
    ```
* pass by reference
    ``` go
    type Counter struct {
        count int
    }
    
    func increase(cnt *Counter) int {
        cnt.count++
        return cnt.count
    }
    
    func main() {
        c := &Counter{count :10}
        fmt.Println(increase(c))
        fmt.Println(c.count)
    }
    -- Output --
    11
    11
    
    -- Other way pass by reference to above program
    -- rewriting only main function
    func main() {
        c := Counter{count:10}
        // & to reffer it's pointer
        fmt.Println(increase(&c))
        fmt.Println(c.count)
    }
    ```