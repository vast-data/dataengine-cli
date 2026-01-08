---
title: vastde compute-clusters
description: Manage VAST DataEngine compute clusters
---

# vastde compute-clusters

Manage VAST DataEngine compute clusters

## Synopsis

Manage Kubernetes compute clusters for running VAST DataEngine workloads.

Compute clusters are Kubernetes environments where DataEngine functions and pipelines execute.
Each cluster provides the computational resources needed to run your serverless workloads. You can
link external Kubernetes clusters to DataEngine or use VAST-managed clusters.

When linking a cluster, you need to provide Kubernetes API server URL, mTLS authentication credentials,
and specify which namespaces DataEngine can use. The CLI supports both interactive and non-interactive
modes for linking clusters, and can automatically create mTLS credentials from certificate files.

Key operations include linking new clusters, updating cluster configurations, viewing cluster details,
and managing cluster lifecycle.

## Subcommands

- [delete](vastde_compute-clusters_delete.md) - Delete a compute cluster
- [get](vastde_compute-clusters_get.md) - Get a compute cluster details
- [link](vastde_compute-clusters_link.md) - Link a Kubernetes compute cluster
- [list](vastde_compute-clusters_list.md) - List available compute clusters
- [update](vastde_compute-clusters_update.md) - Update a compute cluster

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

