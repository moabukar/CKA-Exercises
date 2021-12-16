# Installing and setting up kubectl (macOS & Linux)

## macOS

- ensure you have installed [HomeBrew](brew.sh)

```sh
brew isntall kubectl
```

## Linux

```sh
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

chmod +x kubectl
mv kubectl /usr/local/bin
```


```sh
mkdir ~/.kube
cd ~/.kube
touch config
```

#### Testing it out

```sh
kubectl get nodes
```