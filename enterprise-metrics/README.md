# Grafana Enterprise Metrics Jsonnet library

> **Note:** This library is in alpha and the structure of the library is subject to breaking changes.

A [Jsonnet](https://jsonnet.org/) library that can be used to configure and deploy Grafana Enterprise Metrics to Kubernetes.

## Getting started

[Jsonnet bundler](https://github.com/jsonnet-bundler/jsonnet-bundler) is used to manage Jsonnet dependencies.
Dependencies will be installed into the `/vendor` directory.
To install the library and its dependencies using Jsonnet bundler:

```console
$ jb install github.com/grafana/jsonnet-libs/enterprise-metrics
```

`k.libsonnet` is a Jsonnet library for Kubernetes. Most other Jsonnet libraries for Kubernetes expect this file to exist in your JSONNET_PATH.

To install `k.libsonnet` for Kubernetes 1.18:

1. Use `jb` to vendor the `k8s-libsonnet` Kubernetes library
```console
$ jb install github.com/jsonnet-libs/k8s-libsonnet/1.18@main
```

2. Ensure the `lib` directory exists
```console
$ mkdir -p lib
```

3. Import the `k8s-libsonnet` Kubernetes library by putting the following Jsonnet into a file called `lib/k.libsonnet`
```jsonnet
(import 'github.com/jsonnet-libs/k8s-libsonnet/1.18/main.libsonnet')
```

## Unit Tests

To run the unit tests:

```console
$ make test
```
