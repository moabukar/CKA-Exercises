## Implementing ETCD backup and restore

```sh
etcdctl snapshot save

etcdctl snapshot status <file-location>

etcdctl snapshot restore

## actual example

ETCDCTL_API=3 etcdctl \
--cacert=/etc/kubernetes/pki/etcd/ca.crt \
--cert=/etc/kubernetes/pki/apiserver-etcd-client.crt \
--key=/etc/kubernetes/pki/apiserver-etcd-client.key snapshot save <destination>

```