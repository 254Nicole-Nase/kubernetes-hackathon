# Part 3 - Storage

## Commands run
```bash
# remove the old database:
kubectl delete deploy products-db
kubectl delete svc products-db

kubectl apply -f kubernetes-hackathon/part1/products-api.yml -f kubernetes-hackathon/part1/products-db.yml -f kubernetes-hackathon/part1/stock-api.yml -f kubernetes-hackathon/part1/web.yml

kubectl rollout restart deploy/products-api deploy/stock-api

```

No visual change from part 2