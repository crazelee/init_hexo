---
title: test-title
date: 2019-02-21 18:05:59
tags: go
categories: 
    - [go,tec,base]
    - test
---
# Hello,GO

### 第一个go程序：hello.go

```go
package main

import "fmt"

func main(){
	fmt.Println("Hello, Go")
}
```

![](media/15419169199743/15507527780944.jpg)

<!--more-->

### go run 一次性调试

```go
$ go run hello.go
Hello, Go
```

**说明**
1. Go是一门编译型语言，Go语言的工具链将源代码及其依赖转换成计算机的机器指令。
2. go run 编译一个或多个以.go结尾的源文件，链接库文件，并运行最终生成的可执行文件。

### go build 直接生成可执行程序
如果不只是一次性实验，你肯定希望能够编译这个程序，保存编译结果以备将来之用。可以用build子命令，将直接生成可执行文件 `hello`，之后直接运行hello可执行文件，结果与go run时是一致的：

```go
$ go build hello.go
$ ./hello
Hello, GO
```

### 基本认知

1. Go语言的代码通过包（package）组织，包类似于其它语言里的库（libraries）或者模块（modules）。每个源文件都以一条 package 声明语句开始，这个例子里就是 package main , 表示该文件属于哪个包，紧跟着一系列导入（import）的包，之后是存储在这个文件里的程序语句。

2. main 包比较特殊。它定义了一个独立可执行的程序，而不是一个库。在 main 里的 main 函数也很特殊，它是整个程序执行时的入口

3. import 声明必须跟在文件的 package 声明之后。

4. gofmt 工具把代码格式化为标准格式，并且 go 工具中的 fmt 子命令会对指定包, 否则默认为当前目录, 中所有.go源文件应用 gofmt 命令。 go clean 移除当前源码包里编译生成的文件，如test.out。

5. 按照惯例，最好在每个包的包声明前添加注释；

6. 空标识符（_下划线）类似垃圾箱，将不需要的变量丢弃，如下，只需要range的value，而不需要索引，则可以赋值给他丢弃

```
for _, arg := range os.Args[1:] {
s += sep + arg
sep = " "
}
```





