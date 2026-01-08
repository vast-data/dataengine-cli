---
title: vastde container-registries delete
description: Delete a container registry
---

# vastde container-registries delete

Delete a container registry

## Synopsis

Delete a container registry from VAST DataEngine.

This command unlinks a container registry identified by its GUID or name, removing it from
DataEngine's available registries. After deletion, the registry can no longer be used for
function deployments.

Important considerations:
- This operation only unlinks the registry from DataEngine; it does not delete the actual
  container registry or its images
- Any functions currently using images from this registry may fail to deploy or scale
- You should migrate functions to use images from other registries before deleting
- The --force flag is available but currently does not skip confirmation (reserved for
  future enhancement)

Use this command when:
- Decommissioning registries that are no longer needed
- Removing registries that have been moved or replaced
- Cleaning up test or development registries

The actual container registry and its images remain intact and accessible outside of
DataEngine. You can re-link the same registry later if needed.

```
vastde container-registries delete [guid|name] [flags]
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

- [vastde container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries

