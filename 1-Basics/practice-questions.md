# Practice questions

Create a pod from the image nginx

```sh

kubectl run nginx --image=nginx

```

Create a pod from the image nginx with the yaml spec and do not apply it (hint : use dry-run)

```sh

kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml

```

Deploy a pod named pod-test using the image nginx:1.2-alpine

```sh

kubectl run pod-test --image=nginx:1.2-alpine

```

