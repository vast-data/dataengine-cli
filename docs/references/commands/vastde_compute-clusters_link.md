---
title: vastde compute-clusters link
description: Link a Kubernetes compute cluster
---

# vastde compute-clusters link

Link a Kubernetes compute cluster

## Synopsis

Link an external Kubernetes cluster to VAST DataEngine for running workloads.

This command registers a Kubernetes cluster with DataEngine, enabling it to execute functions
and pipelines. Linking requires:

1. Kubernetes API server URL (--kube-api-url)
2. mTLS authentication credentials for cluster access:
   - Option A: Provide existing mTLS credentials GUID (--mtls-credentials-guid)
   - Option B: Provide certificate files (--client-key-path, --client-cert-path, --ca-path)
              The CLI will automatically create mTLS credentials from these files
3. Namespaces where DataEngine can deploy workloads (--namespaces)

The command supports interactive mode (--interactive) which prompts for certificate file paths
if not provided via flags. Certificate files must be in PEM format.

After linking, the cluster becomes available for function execution. DataEngine will use the
specified namespaces to deploy function pods and manage workload lifecycle.

Prerequisites:
- Kubernetes cluster must be accessible from DataEngine
- Certificate files must have appropriate permissions for cluster access
- Specified namespaces must exist in the cluster

```
vastde compute-clusters link [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--ca-path` | string | Path to certificate authority file (PEM format) |  |
| `--client-cert-path` | string | Path to client certificate file (PEM format) |  |
| `--client-key-path` | string | Path to client private key file (PEM format) |  |
| `--description` | string | A description of the compute cluster (optional) |  |
| `-i`, `--interactive` | bool | Interactive mode: prompt for missing certificate paths |  |
| `--kube-api-url` | string | Kubernetes API server URL (required) |  |
| `--mtls-credentials-guid` | string | GUID of existing mTLS authentication credentials (optional, if not provided will create new one) |  |
| `--mtls-credentials-name` | string | Name for the mTLS credentials to create (defaults to cluster name + '-credentials') |  |
| `-n`, `--name` | string | A name for the compute cluster (required) |  |
| `--namespaces` | stringSlice | List of Kubernetes namespaces (required) |  |
| `--tags` | stringSlice | Custom tags to apply (optional) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde compute-clusters](vastde_compute-clusters.md) - Manage VAST DataEngine compute clusters

