## Creating a Persistent volume 

```sh

vi pv.yaml

apiVersion: v1
kind: PersistentVolume
metadata:
  name: first-pv
spec:
  storageClassName: manual
  capacity:
    storage: 10Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: /tmp/data

kubectl apply -f pv.yaml

```

## Creating a Persistent Volume Claim (PVC)

```sh

vi pvc.yaml

apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc
spec:
  storageClassName: manual
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: 10Gi

kubectl apply -f pvc.yaml

```

## Using a volume in a pod

```sh

vi pvpod.yaml

kind: Pod
apiVersion: v1
metadata:
  name: pvc-pod
spec:
  containers:
    - name: test1
      image: nginx
      volumeMounts:
      - mountPath: "/data"
        name: vol1
  volumes:
    - name: vol1
      persistentVolumeClaim:
        claimName: pvc

kubectl apply -f pvpod.yaml

```