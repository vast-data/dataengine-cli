---
title: vastde container-registries list
description: List available container registries
---

# vastde container-registries list

List available container registries

## Synopsis

List all container registries linked to your VAST DataEngine environment.

This command displays all registered container registries that can be used for storing and
accessing function images. Each entry shows the registry name, URL, authentication type,
and cluster assignments.

You can control the number of results with pagination parameters (--limit and --cursor).
The output can be formatted as human-readable tables, JSON, or YAML for integration with
automation tools.

Container registries must be properly configured with authentication credentials and linked
to compute clusters before functions can pull images from them. Use this command to verify
registry availability and identify which registries are ready for use.

```
vastde container-registries list [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-l`, `--limit` | int32 | Maximum number of items to display (0 = no limit) | `0` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries

