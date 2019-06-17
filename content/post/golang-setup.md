---
title: "Golang Setup on Ubuntu"
date: 2019-06-16T16:07:54Z
categories: ["golang"]
draft: false
---

####  **Installing Golang on Ubuntu**
> We will be using snappy tool to install go on ubuntu.

Ref: [snappy](https://itsfoss.com/install-snap-linux/)

* Get info for go packages availabe.
    ``` 
    $ snap info go
    
    name:      go
    summary:   Go programming language compiler, linker, stdlib
    publisher: Michael Hudson-Doyle (mwhudson)
    contact:   michael.hudson@ubuntu.com
    license:   unset
    description: |
      This snap provides an assembler, compiler, linker, and compiled libraries for the Go programming
      language.
    commands:
      - go
      - go.gofmt
    snap-id:      Md1HBASHzP4i0bniScAjXGnOII9cEK6e
    tracking:     stable
    refresh-date: 2 days ago, at 07:00 IST
    channels:
      stable:         1.12.6        2019-06-13 (3947) 92MB classic
      candidate:      ^                                    
      beta:           ^                                    
      edge:           devel-7a4d023 2019-06-17 (3978) 92MB classic
      1.12/stable:    1.12.6        2019-06-13 (3947) 92MB classic
      1.12/candidate: ^                                    
      1.12/beta:      ^                                    
      1.12/edge:      ^                                    
      1.11/stable:    1.11.11       2019-06-13 (3945) 82MB classic
      1.11/candidate: 1.11.11       2019-06-12 (3945) 82MB classic
      1.11/beta:      ^                                    
      1.11/edge:      ^                                    
      1.10/stable:    1.10.8        2019-01-24 (3133) 58MB classic
      1.10/candidate: ^                                    
      1.10/beta:      ^                                    
      1.10/edge:      ^                                    
    ```

* Install go
    ```
    $ sudo snap install --classic --channel=1.11/stable go
    
    -- Option "--classic" disables security confinement; to let go have access to system resources.
    -- Otherwise(without option --classic) 
        snaps are installed and mounted in a tightly controlled space: they don’t have access to the vast majority of system resources, 
        they bundle libraries they need and have a read-only file-system. 
        In the snap world, this is the “strict” confinement policy, which is enforced by default.
    -- Option "--channel"
      allow you to specify a channel from which the package is downloaded and installed.
    ```
* vefiry go installation
  ``` 
  $ go version
  go version go1.12.6 linux/amd64
  ```
* GOROOT vs GOPATH env variables.
  ``` 
  -- GOROOT must be set only when installing to a custom location.
  -- The GOPATH environment variable lists places to look for Go code. 
    On Unix, the value is a colon-separated string. On Windows, the value is a semicolon-separated string. 
    On Plan 9, the value is a list. GOPATH must be set to get, build and install packages outside the standard Go tree.
  ```

#### **GOOS & GOARCH** build arguments
Go provides easy to build executable binary for any platform.

For e.g: To build binary for windows
```
-- builds main.exe
$ env GOOS=windows GOARCH=amd64 go build main.go 
$ ls
main.exe main.go
```

#### **Go CLI**
- Project initializatoin
- Build go project
- **go gen** to generate go code
- **go get** to retrieve dependencies
- **go test** 
- **profiling** (like cheking cpu, network usage, memory)
- **go doc** for documentaion
