# <center>GO命令</center>

#### Go编译Linux

>1.编译项目名称
```
SET CGO_ENABLED=0
SET GOARCH=amd64
SET GOOS=linux
go build
```

>2.编译自定义名称
```SET CGO_ENABLED=0
SET GOARCH=amd64
SET GOOS=linux
go build main.go
```

#### 编译windows文件
```
SET CGO_ENABLED=1
SET GOARCH=
SET GOOS=windows
go build
```