# Cilium Update

```
helm repo add hashicorp https://helm.releases.hashicorp.com
helm repo update
helm template vault hashicorp/vault --version 0.27.0 -f helm/values.yaml --namespace vault > bundle.yaml
```