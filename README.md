Testing argocd

## Local testing

```bash
minikube start
minikube addons enable metrics-server

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl apply -f application.yml
```
