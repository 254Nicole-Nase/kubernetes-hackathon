# Part 2 - Configuration

## Commands run
```bash

kubectl apply -f kubernetes-hackathon/part3/products-api.yml -f kubernetes-hackathon/part3/products-db.yml -f kubernetes-hackathon/part3/stock-api.yml -f kubernetes-hackathon/part3/web.yml

kubectl get pods 

kubectl port-forward svc/web 8080:80
```

![Part 2](image-1.png)