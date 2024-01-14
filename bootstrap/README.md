# Bootstraping Manual

## Cluster init

You need to configure containerd to enable correct device ownership to use block volumes. Set this value in /etc/containerd/config.toml :
```toml
[plugins]
  [plugins."io.containerd.grpc.v1.cri"]
    device_ownership_from_security_context = true
```

Now, configure the first control plane:
```bash
# kubeadm config file path = ./kubernetes/config.yaml
# You need to copy the file on the remote control-plane
kubeadm init --config FILE
```

## CNI (Cilium)

```bash
kubectl apply -f cilium/
```

## Remove control-plane taint

```
kubectl taint nodes <NODE_NAME> node-role.kubernetes.io/control-plane:NoSchedule-
```


## Flucd (GitOps)

Deploy fluxcd and gitops resources in the cluster
```bash
kubectl kustomize fluxcd/ | kubectl apply -f -
```

# DNS
Deploy fluxcd and gitops resources in the cluster
```bash
kubectl apply -f kubernetes/coredns-config.yaml
```
