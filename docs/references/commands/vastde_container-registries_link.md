---
title: vastde container-registries link
description: Link a container registry
---

# vastde container-registries link

Link a container registry

## Synopsis

Link an external container registry to VAST DataEngine for storing function images.

This command registers a container registry with DataEngine, enabling it to store and serve
function container images. Linking requires:

1. Registry URL (--url): The container registry endpoint
2. Primary compute cluster (--primary-cluster): The main cluster that will pull images
3. Authentication configuration (--auth-type):
   - none: No authentication required
   - secret: Use Kubernetes secret (specify with --secret)
   - password: Use username/password (specify with --username and --password)

Optional settings:
- Additional compute clusters (--additional-clusters, --additional-namespaces)
- Email for registry authentication (--email)
- Custom tags and description

The registry must be accessible from the specified compute clusters. DataEngine will use
the provided authentication to pull function images during deployment.

Supported registry types include Docker Hub, Amazon ECR, Google GCR, Azure ACR, and
private Docker registries. Ensure the registry URL is correct and authentication
credentials have sufficient permissions to pull images.

Prerequisites:
- Compute cluster must be linked to DataEngine first
- Registry must be accessible from the cluster network
- Authentication credentials must have image pull permissions

```
vastde container-registries link [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--additional-clusters` | stringSlice | Additional Kubernetes cluster names or VRNs |  |
| `--additional-namespaces` | stringSlice | Additional Kubernetes namespaces |  |
| `--auth-type` | string | Authentication type (none, secret, password) | `none` |
| `--description` | string | A description of the resource (optional) |  |
| `--email` | string | User email for authentication |  |
| `-n`, `--name` | string | A name for the resource (required) |  |
| `--password` | string | Password for authentication |  |
| `--primary-cluster` | string | Primary Kubernetes cluster name or VRN |  |
| `--primary-namespace` | string | Primary Kubernetes namespace |  |
| `--secret` | string | Secret name for authentication |  |
| `--tags` | stringSlice | Custom tags to apply (optional) |  |
| `--url` | string | URL to the container registry (required) |  |
| `--username` | string | Username for authentication |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries

