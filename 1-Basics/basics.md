#### Creating your first pod

```sh

vi firstpod.yaml 

apiVersion: v1
kind: Pod
metadata:
  name: nginxwebserver
spec:
  containers:
  -  image: nginx
     name: first

kubectl apply -f firstpod.yaml

```

#### Creating your first deployment

```sh

vi firstdeploy.yaml 

apiVersion: apps/v1
kind: Deployment
metadata:
  labels:
    app: deploy1
  name: deploy1
spec:
  replicas: 1
  selector:
    matchLabels:
      app: deploy1
  template:
    metadata:
      labels:
        app: deploy1
    spec:
      containers:
      - image: nginx
        name: nginx


kubectl apply -f firstdeploy.yaml
```
