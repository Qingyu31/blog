##go build的选择编译

golang通过文件名的后缀进行选择编译

通过查阅官方文档https://golang.org/pkg/go/build/和部分源码：

文件名匹配规则
在去除扩展名和_test(单元测试文件)后剩余的文件名符合以下几种定义之一

* *\_GOOS

* *\_GOARCH

* *\_GOOS\_GOARCH

其中GOOS和GOARCH需要是Golang已知的操作系统和硬件构架


定义最终来自于https://github.com/golang/go/blob/master/src/go/build/syslist.go

```go
const goosList = "android darwin dragonfly freebsd linux nacl netbsd openbsd plan9 solaris windows zos "</br>
const goarchList = "386 amd64 amd64p32 arm armbe arm64 arm64be ppc64 ppc64le mips mipsle mips64 mips64le mips64p32 mips64p32le ppc s390 s390x sparc sparc64 "
```