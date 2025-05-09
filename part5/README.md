# Part 5 - Productionizing

## Commands run
If no ingress-controller, deploy the official NGINX Ingress controller using this command:
```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.6/deploy/static/provider/cloud/deploy.yaml
```
Wait for the controller to become ready

```bash
kubectl kubectl apply -f part5/
```

```bash
kubectl get pods
```
Access the Application
Open http://widgetario.local for the web UI.

Open http://api.widgetario.local/products for the products API.

No changes in web page
