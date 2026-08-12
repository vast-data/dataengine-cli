---
title: vastde container-registries get
description: Get a container registry details
---

# vastde container-registries get

Get a container registry details

## Synopsis

Get detailed information about a specific container registry.

This command retrieves comprehensive details about a single container registry identified by either
its GUID or name. The registry details include:

- Registry name and GUID
- Registry URL
- Authentication configuration (type, credentials)
- Primary Kubernetes cluster assignment
- Additional Kubernetes clusters
- Associated tags and metadata
- Creation and modification timestamps

Use this command to verify registry configuration, check authentication settings, or inspect
registry properties before using it for function deployments.

```
vastde container-registries get [guid|name]
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries

