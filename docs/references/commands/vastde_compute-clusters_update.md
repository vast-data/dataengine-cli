---
title: vastde compute-clusters update
description: Update a compute cluster
---

# vastde compute-clusters update

Update a compute cluster

## Synopsis

Update configuration of an existing compute cluster.

This command modifies properties of a linked compute cluster identified by its GUID or name.
You can update the following properties:

- Description (--description)
- Tags (--tags)
- Kubernetes API server URL (--kube-api-url)
- mTLS authentication credentials (--mtls-credentials-guid)
- Configured namespaces (--namespaces)

Updates can be specified via command-line flags or a YAML configuration file (--file).
When using a file, command-line flags take precedence over file values, allowing selective
overrides.

Note: The cluster name cannot be changed after creation. To change the name, you must delete
and recreate the cluster.

The update operation uses a read-modify-write pattern: it fetches the current configuration,
applies your changes, and updates the cluster. Only the properties you explicitly specify
will be modified; other properties retain their current values.

```
vastde compute-clusters update [guid|name] [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--description` | string | A description of the compute cluster |  |
| `-f`, `--file` | string | Path to YAML file containing update configuration |  |
| `--kube-api-url` | string | Kubernetes API server URL |  |
| `--mtls-credentials-guid` | string | GUID of mTLS authentication credentials |  |
| `--namespaces` | stringSlice | List of Kubernetes namespaces |  |
| `--tags` | stringSlice | Custom tags to apply |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde compute-clusters](vastde_compute-clusters.md) - Manage VAST DataEngine compute clusters

