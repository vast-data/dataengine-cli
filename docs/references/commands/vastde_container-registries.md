---
title: vastde container-registries
description: Manage VAST DataEngine container registries
---

# vastde container-registries

Manage VAST DataEngine container registries

## Synopsis

Manage container registries for storing and accessing DataEngine function images.

Container registries store the Docker images that contain your function code and dependencies.
DataEngine supports linking external container registries (like Docker Hub, Amazon ECR, Google GCR)
or using VAST-managed registries.

When creating functions, you must specify which container registry contains the function image.
The registry must be linked to DataEngine with appropriate authentication credentials before
functions can pull images from it.

Key operations include linking new registries, updating registry credentials, viewing registry
details, and managing the registry lifecycle. Registries require authentication configuration
such as username/password or access tokens depending on the registry type.

## Subcommands

- [delete](vastde_container-registries_delete.md) - Delete a container registry
- [get](vastde_container-registries_get.md) - Get a container registry details
- [link](vastde_container-registries_link.md) - Link a container registry
- [list](vastde_container-registries_list.md) - List available container registries
- [update](vastde_container-registries_update.md) - Update a container registry

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

