---
title: vastde compute-clusters delete
description: Delete a compute cluster
---

# vastde compute-clusters delete

Delete a compute cluster

## Synopsis

Delete a compute cluster from VAST DataEngine.

This command unregisters a compute cluster identified by its GUID or name, removing it from
DataEngine's available compute resources. After deletion, the cluster can no longer execute
functions or pipelines.

Important considerations:
- This operation only unlinks the cluster from DataEngine; it does not delete the actual
  Kubernetes cluster or its resources
- Any functions or pipelines currently deployed to this cluster may become inaccessible
- You should migrate workloads to other clusters before deleting
- The --force flag is available but currently does not skip confirmation (reserved for
  future enhancement)

Use this command when decommissioning clusters or removing clusters that are no longer
needed for DataEngine workloads. The Kubernetes cluster itself remains intact and can be
re-linked to DataEngine if needed later.

```
vastde compute-clusters delete [guid|name] [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-f`, `--force` | bool | Skip confirmation prompt |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde compute-clusters](vastde_compute-clusters.md) - Manage VAST DataEngine compute clusters

