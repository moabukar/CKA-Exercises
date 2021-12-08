# Kubernetes commands - a set of commands that may come in handy.

for your local machine - New versions of K8s exams already has auto-complete setup on clusters

## Autocomplete
```sh
source <(kubectl completion bash) # setup autocomplete in bash into the current shell, bash-completion package should be installed first.
echo "source <(kubectl completion bash)" >> ~/.bashrc # add autocomplete permanently to your bash shell.

alias k=kubectl
complete -F __start_kubectl k
```

## Aliases
```sh
alias k='kubectl'
alias kg='kubectl get'
alias ke='kubectl edit'
alias kd='kubectl describe'
alias kdd='kubectl delete'
alias kgp='kubectl get pods'
alias kgd='kubectl get deployments'
alias kns='kubens'
alias kcx='kubectx'
alias wkgp='watch kubectl get pod'
```


# Pods

```sh
kubectl get pods
kubectl get pods --all-namespaces OR kubectl get pods -A
kubectl get pod <podname> -o wide
kubectl get pod <podname> -o wide
kubectl describe pod <podname>
```

# Creating Deployments
```sh
kubectl run <podname> --image=nginx
```

# Scaling of pods

```sh
kubectl scale deploy <deploymentname> --replicas=<No.ofPods>
```


# Services

## Listing the services
```sh
kubectl get services
```

## Exposing Pods as services i.e. creating endpoints
```sh
kubectl expose deploy <deployname> --port=80 --type=NodePort > type can be ClusterIP/NodePort/LoadBalancer (if using a cloud-native cluster)
```

# ConfigMaps

```sh
kubectl create cm <configmapname> --from-file=<file.txt>
kubectl get cm <configmapname> -o yaml
```

# Volumes

```sh
kubectl get pv
kubectl get pvc
```

# Ingress
```sh
kubectl get ingress OR kubectl get ing
kubectl 
```

# Horizontal Pod Autoscaler HPA
```sh
kubectl get hpa
kubectl autoscale deployment <name> --min=2 --max=8
kubectl autoscale deployment <name> --max=3 --cpu-percent=60
```
# Role-Based Access Control
```sh
kubectl create role <rolename> --verb=create,get,update,delete --resource=pods,deployments,services
kubectl create rolebinding foo --role=<rolename> --serviceaccount=namespace:serviceaccountname
kubectl get rolebinding foo -o yaml

# Any Troubleshooting useful commands

```sh
kubectl logs <podname>
kubectl get events
kubectl exec -it <podname> -- sh
```

