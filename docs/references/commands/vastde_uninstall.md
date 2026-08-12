---
title: vastde uninstall
description: Uninstall DataEngine from a Kubernetes cluster
---

# vastde uninstall

Uninstall DataEngine from a Kubernetes cluster

## Synopsis

Remove the VAST DataEngine Helm release from the cluster.

Examples:

  Uninstall DataEngine:
    $ vastde uninstall

  Uninstall and wait for all resources to be deleted:
    $ vastde uninstall --wait

## Usage

```
vastde uninstall [options]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--debug` | bool | Enable verbose Helm debug logging |  |
| `--kubeconfig` | string | Path to the kubeconfig file (defaults to $KUBECONFIG or ~/.kube/config) |  |
| `-n`, `--namespace` | string | Target Kubernetes namespace | `vast-dataengine` |
| `--release-name` | string | Helm release name | `vast-dataengine` |
| `--timeout` | duration | Timeout for --wait | `5m0s` |
| `--wait` | bool | Wait for resources to be deleted |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: `json`, `yaml`, `human` | `human` |
| `--silent` | bool | Suppress UI outputs, such as spinner and success messages |  |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

