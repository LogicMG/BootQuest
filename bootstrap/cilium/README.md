# Cilium Update

```
helm repo add cilium https://helm.cilium.io/
helm repo update
API_SERVER_IP=192.168.253.252
API_SERVER_PORT=6443
helm template cilium cilium/cilium --version 1.14.5 \
    --namespace kube-system \
    --set l2announcements.enabled=true \
    --set socketLB.hostNamespaceOnly=true \
    --set kubeProxyReplacement=true \
    --set k8sServiceHost=${API_SERVER_IP} \
    --set k8sServicePort=${API_SERVER_PORT} > bundle.yaml
```