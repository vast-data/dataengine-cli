---
title: vastde compute-clusters list
description: List available compute clusters
---

# vastde compute-clusters list

List available compute clusters

## Synopsis

List all compute clusters available in your VAST DataEngine environment.

This command displays all registered compute clusters that can execute DataEngine functions and
pipelines. Each entry shows the cluster name, GUID, status, and key configuration details.

You can control the number of results with pagination parameters (--limit and --cursor). The
output can be formatted as human-readable tables, JSON, or YAML for integration with other tools.

Compute clusters must be in a healthy state and properly configured before they can execute
workloads. Use this command to verify cluster availability and identify which clusters are
ready for function deployment.

```
vastde compute-clusters list [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-l`, `--limit` | int32 | Maximum number of items to display (0 = no limit) | `0` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde compute-clusters](vastde_compute-clusters.md) - Manage VAST DataEngine compute clusters

