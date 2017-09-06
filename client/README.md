#Telemetry客户端

client实现了基本的streaming telemetry的客户端功能。当前主要用于设备端的telemetry功能测试。

## 入门指南

编译使用客户端，需要安装go语言([golang.org](golang.org/dl))。
按照下述步骤进行编译安装。

- 1. 新建目录xxx作为编译目录
  <pre>
mkdir xxxx
export GOROOT=~/go
export GOPATH=~/xxxx
  </pre>
- 2. 下载streaming telemetry client，同时会下载rpc/format等。
<pre>
go get github.com/richard28530/streaming_telemetry
</pre>
- 3. 下载go依赖，client依赖如下
<pre>
go get github.com/golang/glog
go get github.com/golang/protobuf/proto
go get github.com/golang/protobuf/protoc-gen-go
go get github.com/golang/protobuf/ptypes
go get golang.org/x/net/context
go get google.golang.org/grpc/codes
go get google.golang.org/grpc/credentials
go get google.golang.org/grpc
</pre>
- 4. 编译
<pre>
go build src/github.com/richard28530/streaming_telemetry/client/main.go
</pre>

## 使用方法

### Get

Get performs a single OpenConfig Get request for the provided query paths. The paths must be comma separated and "/" must be used as a path separator.

```
./main -target=127.0.0.1:10162 -tls -user=test -password=test -query=/peripherals -outfile=/tmp/foo

./main -target=127.0.0.1:10162 -tls -user=test -password=test -query=/interface/gigabit_ethernet/[te-1/1/5]
```

### Subscribe

Subscribe performs an OpenConfig Subscribe request for the provided query paths. The paths must be comma separated and "/" must be used as a path separator. If -subscribe_once is provided the subscription will be closed once a SyncResponse message has been returned by the server.

```
./main -target=127.0.0.1:10162 -tls -user=test -password=test -query=/interface/gigabit_ethernet/[te-1/1/5] -use_subscribe -outfile=/tmp/foo -subscribe_once
```

## 其他
* (可选)重新生成rpc go代码

```
cd $GOPATH/github.com/richard28530/streaming_telemetry/rpc
protoc --go_out=plugins=grpc:. *.proto
```
