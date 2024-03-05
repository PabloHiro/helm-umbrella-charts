# Local Ready AWX chart

## Prerequisites

* Working kubernetes cluster (tested on [Kind](https://kind.sigs.k8s.io/)!)
* Helm CLI

## Installation

```
helm dependency build
kubectl create ns awx
helm template . -n awx | kubectl -n awx apply -f -
```

## Access de UI

Get the admin password and access via port-forwarding

```
kubectl -n awx get secret awx-admin-password --template={{.data.password}} | base64 --decode
kubectl -n awx port-forward svc/awx-service 8080:80
```

## Update

Replace the field `version` in the `Chart.yaml` file to point to the latest version of the operator.

