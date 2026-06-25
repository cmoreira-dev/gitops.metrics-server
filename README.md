# gitops.metrics-server

GitOps repo for [Kubernetes Metrics Server](https://github.com/kubernetes-sigs/metrics-server) on the homelab Talos cluster.

Enables the `metrics.k8s.io` API required by HPA and `kubectl top`.

## Structure

```
argocd/                  ArgoCD Application (deployed by SCMProvider ApplicationSet)
helm/metrics-server/     Wrapper chart (upstream: kubernetes-sigs/metrics-server)
```

## Talos-specific configuration

- `--kubelet-insecure-tls`: kubelet uses self-signed certificates on self-hosted clusters
- `--kubelet-preferred-address-types=InternalIP`: avoids hostname resolution issues on Talos nodes