Testing argocd

## Local testing

```bash
minikube start
minikube addons enable metrics-server

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl apply -f application.yml
```

### Access argo cd

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
argocd admin initial-password -n argocd
```

### Access graphana

```bash
kubectl port-forward -n prometheus deployments/prometheus-grafana 3000
```
username: admin
password: prom-operator
