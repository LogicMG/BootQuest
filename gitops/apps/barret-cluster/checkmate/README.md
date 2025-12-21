# Checkmate bootstrap

1. Create namespace:
```
kubectl create ns checkmate
```

2. Create checkmate secret:
```
kubectl create secret generic sensitive -n checkmate --from-literal=JWT_SECRET=<YOUR_JWT_SECRET> --from-literal=DB_CONNECTION_STRING=mongodb://checkmate-mongodb.namespace.svc:27017/uptime_db
```
