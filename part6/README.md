# Part 6 - Observability

## Commands Run

### Setup Helm. Prometheus, Grafana, Kibana
```bash

helm version
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo update
kubectl create namespace monitoring

helm install kube-prometheus-stack prometheus-community/kube-prometheus-stack --namespace monitoring

kubectl --namespace monitoring get pods

kubectl port-forward svc/kube-prometheus-stack-prometheus -n monitoring 9090:9090
kubectl port-forward svc/kube-prometheus-stack-grafana -n monitoring 3000:80

kubectl apply -f products-api.yml\
kubectl apply -f stock-api.yml\
kubectl apply -f web.yml

kubectl rollout restart deploy/products-api\
kubectl rollout restart deploy/stock-api\
kubectl rollout restart deploy/web

kubectl get secret --namespace monitoring kube-prometheus-stack-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

helm install elasticsearch elastic/elasticsearch

helm repo add elastic https://helm.elastic.co

helm install elasticsearch elastic/elasticsearch

helm repo add stable https://charts.helm.sh/stable

helm install fluentd stable/fluentd
helm install kibana elastic/kibana


```