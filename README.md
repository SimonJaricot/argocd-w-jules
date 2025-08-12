# ArgoCD with Google Jules

## Create a local cluster with Kind
### Prerequisites

- Docker installed [link](https://docs.docker.com/get-docker/)
- Kind installed [link](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)

```
# create a cluster with the following config
kind create cluster --config kind-config.yaml

# install argocd on the cluster
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# allow port forwarding to the ArgoCD service
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
