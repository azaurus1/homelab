# homelab

Below is the yaml file for the root-app in ArgoCD (Using App of Apps pattern)


```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: root-app
  namespace: argocd
spec:
  destination:
    name: in-cluster
    namespace: default
    server: ''
  source:
    path: root
    repoURL: 'https://github.com/azaurus1/homelab/'
    targetRevision: HEAD
  project: default
  syncPolicy:
    automated:
      prune: false
      selfHeal: false

```

Applications are mapped to the following nodePorts:

Jellyfin -> 30000
qbittorrent -> 30001
radarr -> 30002
sonarr -> 30003

