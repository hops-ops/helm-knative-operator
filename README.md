# helm-knative-operator

A Crossplane Configuration package that installs the Knative Operator Helm chart with a minimal, stable interface.

## Overview

`helm-knative-operator` renders a single Helm release for Knative Operator. It exposes only the inputs needed
for chart values, namespace, and release name, keeping the interface stable while allowing full Helm overrides.

## Features

- **Minimal Helm interface**: values and overrideAllValues with stable defaults
- **Predictable naming**: defaults to `<clusterName>-knative-operator` in the `knative-operator` namespace
- **GitOps friendly**: ships a `.gitops/` deploy chart

## Prerequisites

- Crossplane installed in the cluster
- Crossplane providers:
  - `provider-helm` (>=v1.0.2)
- Crossplane function:
  - `function-auto-ready` (>=v0.6.0)

## Quick Start

```yaml
apiVersion: pkg.crossplane.io/v1
kind: Configuration
metadata:
  name: helm-knative-operator
spec:
  package: ghcr.io/hops-ops/helm-knative-operator:latest
```

```yaml
apiVersion: helm.hops.ops.com.ai/v1alpha1
kind: KnativeOperator
metadata:
  name: knative-operator
  namespace: example-env
spec:
  clusterName: example-cluster
  values:
    operator:
      replicas: 1
```

## Development

```bash
make render
make validate
make test
```
