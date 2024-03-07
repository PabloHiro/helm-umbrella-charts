# Installation

```shell
helm dependency build
kubectl create ns awx
helm template . -n awx | kubectl -n awx apply -f -
```

# Access de UI

Get the admin password and access via port-forwarding

```shell
kubectl -n awx get secret awx-admin-password --template={{.data.password}} | base64 --decode
kubectl -n awx port
```
