---
title: vastde status
description: Get the status of a DataEngine release
---

# vastde status

Get the status of a DataEngine release

## Synopsis

Get the status of a DataEngine release.

The chart name is embedded in the CLI binary at build time.

Examples:

  Shows status of the DataEngine release: 
    $ vastde status

## Usage

```
vastde status [options]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--debug` | bool | Enable verbose Helm debug logging |  |
| `--kubeconfig` | string | Path to the kubeconfig file (defaults to $KUBECONFIG or ~/.kube/config) |  |
| `--namespace` | string | Target Kubernetes namespace | `vast-dataengine` |
| `--release-name` | string | Helm release name | `vast-dataengine` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: `json`, `yaml`, `human` | `human` |
| `--silent` | bool | Suppress UI outputs, such as spinner and success messages |  |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

