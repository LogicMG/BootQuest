# Cilium Update

```
helm repo add hashicorp https://helm.releases.hashicorp.com
helm repo update
helm template cilium cilium/cilium --version 1.14.5 \
    --namespace kube-system \
    --set l2announcements.enabled=true \
    --set kubeProxyReplacement=true \
    --set k8sServiceHost=${API_SERVER_IP} \
    --set k8sServicePort=${API_SERVER_PORT} > bundle.yaml
```