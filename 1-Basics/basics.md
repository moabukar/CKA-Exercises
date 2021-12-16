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



```
