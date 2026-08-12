---
title: vastde container-registries update
description: Update a container registry
---

# vastde container-registries update

Update a container registry

## Synopsis

Update configuration of an existing container registry.

This command modifies properties of a linked container registry identified by its GUID or name.
You can update the following properties:

- Description (--description)
- Tags (--tags)
- Registry URL (--url)
- Authentication configuration (--auth-type, --secret, --username, --password, --email)
- Primary compute cluster assignment (--primary-cluster, --primary-namespace)
- Additional compute clusters (--additional-clusters, --additional-namespaces)

Updates can be specified via command-line flags or a YAML configuration file (--file).
When using a file, command-line flags take precedence over file values, allowing selective
overrides.

Note: The registry name cannot be changed after creation. To change the name, you must
delete and recreate the registry.

The update operation uses a read-modify-write pattern: it fetches the current configuration,
applies your changes, and updates the registry. Only the properties you explicitly specify
will be modified; other properties retain their current values.

Use this command to:
- Update authentication credentials
- Change cluster assignments
- Modify registry URL if moved
- Update metadata and tags

```
vastde container-registries update [guid|name] [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--additional-clusters` | stringSlice | Additional Kubernetes cluster names or VRNs |  |
| `--additional-namespaces` | stringSlice | Additional Kubernetes namespaces |  |
| `--auth-type` | string | Authentication type (none, secret, password) |  |
| `--description` | string | A description of the resource |  |
| `--email` | string | User email for authentication |  |
| `-f`, `--file` | string | Path to YAML file containing update configuration |  |
| `--password` | string | Password for authentication |  |
| `--primary-cluster` | string | Primary Kubernetes cluster name or VRN |  |
| `--primary-namespace` | string | Primary Kubernetes namespace |  |
| `--secret` | string | Secret name for authentication |  |
| `--tags` | stringSlice | Custom tags to apply |  |
| `--url` | string | URL to the container registry |  |
| `--username` | string | Username for authentication |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries

