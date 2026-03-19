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

## Usage

```
vastde container-registries link [options]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--additional-clusters` | stringSlice | Additional Kubernetes cluster names or VRNs |  |
| `--additional-namespaces` | stringSlice | Additional Kubernetes namespaces |  |
| `--auth-type` | string | The type of authentication that DataEngine should use to pull function images during deployment. Supported values: `none`= no authentication required, `secret`=authenticate with a specified Kubernetes secret, `password`=authenticate with a secret generated from specified credentials. See also `--email`, `--password`, `--username`, `--secret`. | `none` |
| `--description` | string | A description for the container registry resource |  |
| `--email` | string | User email for authentication. Applicable and optional if `--auth-type`=`password` |  |
| `-n`, `--name` | string | A name for the container registry resource |  |
| `--password` | string | Password for authentication. Required if `--auth-type`=`password` |  |
| `--primary-cluster` | string | The name or VRN of the main Kubernetes cluster that will pull images from the container registry |  |
| `--primary-namespace` | string | Primary Kubernetes namespace |  |
| `--secret` | string | An existing Kubernetes secret for authentication. Required if `--auth-type`=`secret` |  |
| `--tags` | stringSlice | Custom tags to apply |  |
| `--url` | string | The URL of the container registry endpoint |  |
| `--username` | string | Username for authentication. Required if `--auth-type`=`password` |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: `json`, `yaml`, `human` | `human` |
| `--silent` | bool | Suppress UI outputs, such as spinner and success messages |  |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries

