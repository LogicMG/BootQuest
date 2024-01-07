# Cilium Update

```
helm repo add hashicorp https://helm.releases.hashicorp.com
helm repo update
helm template vault hashicorp/vault --version 0.27.0 -f helm/values.yaml --namespace vault > bundle.yaml
```

## Bootstrap vault for the first time

In the pod shell :
```
VAULT_ADDR=https://192.168.253.152 vault operator init -key-shares=3 -key-threshold=2
```