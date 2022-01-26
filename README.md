# argocd

```bash

# source https://www.arthurkoziel.com/setting-up-argocd-with-helm/

# if ur using kind as test cluster env
kind create cluster --name my-cluster
kind delete cluster --name my-cluster

# install argocd via helm
helm install argocd argocd --namespace=argocd --create-namespace

# get argocd ui admin password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

# setup port-forward for temporary access
kubectl port-forward service/argo-cd-argocd-server -n argocd 8080:443

```