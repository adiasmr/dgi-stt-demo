### Important
This repository might only be valid in the context of the DGI STT course, it expects a production-ready cluster (cert-manager, ingress-controller, storageclass...).

It contains all neccessary k8s resources templates and helm charts values (helm values need to be adjusted) for DGI STT workshop.

### Useful commands
These commands are not guided labs, the purpose is to show an example of use

# kubectl
```
kubectl get namespace #replace namespace by 'pods', 'services', 'ingress', 'configmap', .....
kubectl create namespace
kubectl create deployment nginx --image=nginx:latest --dry-run=client -o yaml > nginx-deployment.yaml
kubectl apply -f nginx-deployment.yaml
kubectl expose deployment nginx --port 80 --dry-run=client -o yaml > nginx-svc.yaml
kubectl scale --replicas=7 deployment nginx
kubectl create configmap --from-file=index.html
```
# helm
```
helm repo add postgresql https://charts.bitnami.com/bitnami
helm install postgresql postgresql/postgresql
helm upgrade postgresql postgresql/postgresql -f helm/values/postgresql.yaml
helm repo update
helm list
helm get values postgresql
helm get manifest postgresql
```