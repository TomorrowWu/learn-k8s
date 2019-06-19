
```
kubectl get endpoints hostnames
NAME        ENDPOINTS
hostnames   10.244.0.5:9376,10.244.0.6:9376,10.244.0.7:9376


kubectl get svc hostnames
NAME        TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
hostnames   ClusterIP   10.0.1.175   <none>        80/TCP    5s

$ curl 10.0.1.175:80
hostnames-0uton

$ curl 10.0.1.175:80
hostnames-yp2kp

$ curl 10.0.1.175:80
hostnames-bvc05
```
- Service 提供的是 Round Robin 方式的负载均衡
