# Enforcement

[Enforcement](https://github.com/globocom/enforcement-service) is a service developed to automate the installation of packages considered mandatory in clusters created by Rancher. It does this by integrating Rancher with the ArgoCD GitOps platform.

## Installation


```bash
# Testing configuration
$ helm install my-release globocom/enforcement
```

```bash
# Production configuration
$ helm install my-release globocom/enforcement --values values-production.yaml
```

## Introduction
