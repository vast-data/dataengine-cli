---
title: vastde upgrade
description: Upgrade DataEngine on a Kubernetes cluster
---

# vastde upgrade

Upgrade DataEngine on a Kubernetes cluster

## Synopsis

Upgrade an existing VAST DataEngine installation using the embedded Helm chart.

By default, values are reset to the chart defaults, then the last release's
values are reapplied, and any --set / -f overrides are merged on top
(--reset-then-reuse-values).

Examples:

  Upgrade DataEngine to the embedded chart version:
    $ vastde upgrade

  Upgrade with additional values:
    $ vastde upgrade --set collector.replicas=3

  Reset all values to chart defaults:
    $ vastde upgrade --reset-values

  Preview the upgrade:
    $ vastde upgrade --dry-run

## Usage

```
vastde upgrade [options]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--chart-directory` | string | Use local chart directory instead of embedded chart |  |
| `--debug` | bool | Enable verbose Helm debug logging |  |
| `--dry-run` | bool | Render manifests without applying |  |
| `--dry-run-helm-values` | bool | Print non-default Helm values without applying |  |
| `--history-max` | int | Maximum number of release revisions to keep (0 = no limit) | `10` |
| `--kubeconfig` | string | Path to the kubeconfig file (defaults to $KUBECONFIG or ~/.kube/config) |  |
| `--list-versions` | bool | List available embedded chart versions |  |
| `-n`, `--namespace` | string | Target Kubernetes namespace | `vast-dataengine` |
| `--release-name` | string | Helm release name | `vast-dataengine` |
| `--reset-then-reuse-values` | bool | Reset to chart defaults, then apply last release's values and merge overrides | `true` |
| `--reset-values` | bool | Reset helm values to the chart defaults |  |
| `--reuse-values` | bool | Reuse the helm values from the latest release unless overridden |  |
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

