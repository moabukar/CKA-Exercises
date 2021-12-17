# Useful commands

## General

```sh
# Lists the nodes
kubectl get nodes

# Shows addresses of the master and other services
kubectl get cluster-info

# Lists the pods
kubectl get pods 

# Lists the pods with more details
kubectl get pods -o wide

# Lists the pods with more detauls in all namespace
kubectl get pods -o wide --all-namepsace OR kubectl get pods -o wide -A

# Lists the services with more detauls in all namespace
kubectl get svc -o wide --all-namepsace OR kubectl get pods -o wide -A

```

## Workloads & Scheduling 

```sh
Example deployment spec

apiVersion: apps/v1
kind: Deployment
metadata:
    name: deploy-test
    labels:
        app: nginx
spec:
  replicas: 4
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.19
        ports:
        - containerPort: 80

```

```

kubectl apply -f deploy.yaml 

kubectl get deploy

kubectl edit deploy deploy-test

kubectl describe deployment

kubectl rollout status deploy deploy-test

kubectl rollout undo deploy deploy-test
```

## Useful imperative commands

```sh

kubectl create deploy deploy-test --image=nginx --dry-run=client -o yaml > deploy1.yaml

kubectl run pod-test --image=nginx --dry-run=client -o yaml > pod1.yaml

kubectl expose deploy deploy-test --name=service-test type=NodePort --port=80 --dry-run=client -o yaml > service1.yaml

```