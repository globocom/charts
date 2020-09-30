# Enforcement

[Enforcement](https://github.com/globocom/enforcement-service) is a service developed to automate the installation of packages considered mandatory in clusters created by Rancher. It does this by integrating Rancher with the ArgoCD GitOps platform.


## Introduction

This chart initializes an Enforcement deployment on a Kubernetes cluster using the Helm package manager.

## Prerequisites

- Kubernetes 1.12+
- Helm 2.11+ or Helm 3.0-beta3+

## Installation

```bash
# Testing configuration
$ helm install my-release globocom/enforcement
```

```bash
# Production configuration
$ helm install my-release globocom/enforcement --values values-production.yaml
```
The command deploys Enforcement on the Kubernetes cluster in the default configuration. The [Parameters](#parameters) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters
