+++
date = "2016-09-15T13:49:29-04:00"
tags = []
title = "Installing Go on a Mac"
share = true
summary = "test"
+++

## Install Go

```json
brew install go
```

## Prepare Path variables

```json
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

## Test Installation

```json
which go
```


## Writing your first program

Place the following code into a file called `hello_world.go`

```go
 package main

 import "fmt"

 func main() {
   fmt.Println("Hello World!")
 }
```

Save the file and run the command:

```go
go run hello_world.go
```

You should see the following output:

<img src="/images/installing-go/run-output.png" alt="Run Output" />
