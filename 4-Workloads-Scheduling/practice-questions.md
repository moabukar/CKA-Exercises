# Practice questions

A pod named memcached has already been created. 

Create a service  called "service1" to expose the pod through a service at the cluster level on port 6379.

```sh

kubectl expose po memcached --name=service1 --port=6379 --target-port=6379

```