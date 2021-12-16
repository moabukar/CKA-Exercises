# Installing and setting up minikube (macOS & Linux)

## macOS

- ensure you have installed [HomeBrew](brew.sh)

```sh
brew isntall minikube
```

## Linux

```sh
yum -y install docker
systemctl start docker
systemctl enable docker
```

```sh
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

chmod +x minikube
 mv minikube /usr/local/bin
 
minikube start
```

#### Testing it out

```sh
kubectl get nodes
```