---
title: vastde compute-clusters get
description: Get a compute cluster details
---

# vastde compute-clusters get

Get a compute cluster details

## Synopsis

Get detailed information about a specific compute cluster.

This command retrieves comprehensive details about a single compute cluster identified by either
its GUID or name. The cluster details include:

- Cluster name and GUID
- Kubernetes API server URL
- mTLS authentication credentials reference
- Configured namespaces
- Cluster status and health information
- Creation and modification timestamps
- Associated tags and metadata

Use this command to verify cluster configuration, check connectivity settings, or inspect
cluster properties before deploying functions to the cluster.

```
vastde compute-clusters get [guid|name]
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde compute-clusters](vastde_compute-clusters.md) - Manage VAST DataEngine compute clusters

