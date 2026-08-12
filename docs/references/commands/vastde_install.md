---
title: vastde install
description: Install DataEngine on a Kubernetes cluster
---

# vastde install

Install DataEngine on a Kubernetes cluster

## Synopsis

Install VAST DataEngine on a Kubernetes cluster using the embedded Helm chart.

The chart is embedded in the CLI binary at build time. Use --chart-directory
to override with a local chart directory for development.

Examples:

  Install DataEngine with default settings:
    $ vastde install

  Install with custom values file:
    $ vastde install -f my-values.yaml

  Install into a custom namespace:
    $ vastde install --namespace my-namespace

  Preview what would be installed:
    $ vastde install --dry-run

  List available chart versions:
    $ vastde install --list-versions

## Usage

```
vastde install [options]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--chart-directory` | string | Use local chart directory instead of embedded chart |  |
| `--create-namespace` | bool | Create the namespace if it doesn't exist | `true` |
| `--debug` | bool | Enable verbose Helm debug logging |  |
| `--dry-run` | bool | Render manifests without applying |  |
| `--dry-run-helm-values` | bool | Print non-default Helm values without applying |  |
| `--kubeconfig` | string | Path to the kubeconfig file (defaults to $KUBECONFIG or ~/.kube/config) |  |
| `--list-versions` | bool | List available embedded chart versions |  |
| `-n`, `--namespace` | string | Target Kubernetes namespace | `vast-dataengine` |
| `--release-name` | string | Helm release name | `vast-dataengine` |
| `--set` | stringArray | Set values on the command line (key1=val1,key2=val2) |  |
| `--set-file` | stringArray | Set values from files (key=path) |  |
| `--set-string` | stringArray | Set STRING values on the command line |  |
| `--timeout` | duration | Timeout for --wait (default: 5m0s) | `0s` |
| `-f`, `--values` | stringSlice | Specify values in a YAML file (can specify multiple) |  |
| `--version` | string | DataEngine chart version to install (default: latest embedded) |  |
| `--wait` | bool | Wait for resources to be ready |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-o`, `--output` | string | Output format: `json`, `yaml`, `human` | `human` |
| `--silent` | bool | Suppress UI outputs, such as spinner and success messages |  |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

