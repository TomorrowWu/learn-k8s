```
# 部署 Prometheus 项目
kubectl apply -f demos/monitoring/prometheus-operator.yaml
kubectl apply -f demos/monitoring/sample-prometheus-instance.yaml

# Custom Metrics APIServer 部署
kubectl apply -f demos/monitoring/custom-metrics.yaml

kubectl create clusterrolebinding allowall-cm --clusterrole custom-metrics-server-resources --user system:anonymous

kubectl apply -f demos/monitoring/sample-metrics-app.yaml

```
