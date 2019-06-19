
#### 命令式命令行操作
```
Docker Swarm 

docker service create --name nginx --replicas 2  nginx
docker service update --image nginx:1.7.9 nginx
```

#### 命令式配置文件操作
```
kubectl create -f nginx.yaml
kubectl replace -f nginx.yaml
```

#### 声明式 API
- kubectl replace 的执行过程，是使用新的 YAML 文件中的 API 对象，替换原有的 API 对象；而 kubectl apply，则是执行了一个对原有 API 对象的 PATCH 操作。
- kube-apiserver 在响应命令式请求（比如，kubectl replace）的时候，一次只能处理一个写请求，否则会有产生冲突的可能。而对于声明式请求（比如，kubectl apply），一次能处理多个写操作，并且具备 Merge 能力
