# Helm Umbrella Charts

This repository stores ready to use Helm Charts following the Umbrella pattern. Public available Helm Charts are included as dependencies:

```yaml
apiVersion: v2
name: public-chart-umbrella
version: 1.0.0
dependencies:
  - name: public-chart
    version: X.Y.Z 
    repository: https://example.com/public-chart
```

## Prerequisites

* Working kubernetes cluster (tested on [Kind](https://kind.sigs.k8s.io/)!)
* Helm CLI

Kind clusters can be spin up using:

```shell
kind create cluster
```

If using podman:

```shell
KIND_EXPERIMENTAL_PROVIDER=podman kind create cluster
```

Once th cluster is created, it can be accessed using:

```shell
kubectl cluster-info --context kind-kind
```

To delete, use:

```shell
kind delete cluster
```

## Updating a Chart

Replace the field `version` in the `Chart.yaml` file to point to the desired version of the public Chart.


