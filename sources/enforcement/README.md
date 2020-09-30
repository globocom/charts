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

The following table lists the configurable parameters of the Enforcement chart and their default values.

| Parameter | Default |          Description         |
|:---------:|:-------:|:----------------------------:|
| `image.pullPolicy`  | IfNotPresent    | Define image pull policy      |
| `image.tag`                 |      | Enforcement image tag    |  
| `resources.limits.cpu`       | 200m   | Enforcement CPU resource limits       |
| `resources.limits.memory` | 228Mi     | Enforcement Memory resource limits    |
| `resources.requests.cpu`   | 100m     | Enforcement CPU resource requests     |
| `resources.requests.memory` | 128Mi   | Enforcement Memory resource requests  | 
| `nodeSelector` | [] | Pod assignment labels | 
| `tolerations` |  | Tolerance labels for the Enforcement pod |
| `affinity` | {} | Enforcement pod assignment affinity settings  | 
| `spec.sync.minutes` | 1 | Time interval for Enforcement to synchronize with Rancher | 
| `spec.argo.host` | argocd-server.argocd.svc.cluster.local | ArgoCD hostname |  
| `spec.rancher.host` | | Rancher hostname | 
| `spec.rancher.ignore_clusters` | | Name of the Clusters that were created through Rancher and that should be ignored by Enforcement. Ex "cluster1 \, cluster2 \, cluster3". Ex "cluster1 \\, cluster2 \\, cluster3" | 
| `spec.enforcement.secret` | enforcement-secret | Name of the secret that stores the access information for integration with ArgoCD and Rancher. | 
| `spec.enforcement.core.repo` | | URL of the Git repository that contains the Standard enforcements. | 
| `spec.enforcement.core.path` | standard | path to the Git repository that contains the default enforcements | 
| `spec.enforcement.core.name` | standard | Default enforcement name | 
