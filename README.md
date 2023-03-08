### Useful commands
```
kubectl get namespace #replace namespace by 'pods', 'services', 'ingress', 'configmap', .....
kubectl create namespace
kubectl create deployment nginx --image=nginx:latest --dry-run=client -o yaml > nginx-deployment.yaml
kubectl apply -f nginx-deployment.yaml
kubectl expose deployment nginx --port 80 --dry-run=client -o yaml > nginx-svc.yaml
kubectl scale --replicas=7 deployment nginx
kubectl create configmap --from-file=index.html
```