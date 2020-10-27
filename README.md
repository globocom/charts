# **Globo.com** Helm Repository

## Overview

The `globocom/charts` repository provides [Helm](https://github.com/kubernetes/helm) charts for  opensource projects developed by Globo.com.

This repository is organized as follows:

The `source` directory contains Helm chart source, while the `repo/stable` directory contains the packaged Helm chart binaries.  To add the stable repo to local repository list run the following command :
```
helm repo add globocom https://globocom.github.io/charts/repo/stable
```
The repo/stable directory is a Helm repository, and its index.yaml file is built automatically based on the MASTER branch.
