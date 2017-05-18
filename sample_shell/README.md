

### 一些常用的命令

```
go get github.com/micro/micro
```

go to the folder, make the micro tools.


```
micro api
```


run service code 
```
go run examples/greeter/srv/main.go 
```


run the api code
```
go run examples/greeter/api/api.go 
```


default connect the localhost consul



### 怎么做API网关， 假如用 consul做服务发现的话， 要做consuk集群， 假如用其他？？参考下面的命令

-----------------------------------------------------

Can I use something besides Consul?
Yes! The registry for service discovery is completely pluggable as is every other package. Consul was used as the default due to its features and simplicity.

Using etcd

As an example. If you would like to use etcd, import the plugin and set the command line flags on your binary.

import (
		        _ "github.com/micro/go-plugins/registry/etcd"
		)
service --registry=etcd --registry_address=127.0.0.1:2379
Zero Dependency MDNS

Alternatively we can use multicast DNS with the built in MDNS registry for a zero dependency configuration. Just pass --registry=mdns to your application on startup.

--------------------------------------------------



###假如服务发现的时候，服务名称冲突了怎么办？？

需要重启 consul 的server端/， 再重启 api gateway 才可以让服务恢复正常

