---
title: vastde builders
description: View and select VAST DataEngine builder images
---

# vastde builders

View and select VAST DataEngine builder images

## Synopsis

View and select VAST DataEngine builder images from Docker Hub.

This command group provides tools to list, view, and configure builder images
used for building DataEngine functions. Builder images contain the necessary
tools and dependencies for compiling and packaging your serverless functions.

The builder image configuration is stored in your CLI configuration file and
is used by the build process to determine which container image to use when
building your DataEngine functions.

## Examples

```bash
  # List available builder images
  vastde builders list

  # Inspect details about a specific builder image tag
  vastde builders inspect v1.0.60ee8cc7.vast-5.4

  # Set the builder image to use
  vastde builders set v1.0.60ee8cc7.vast-5.4

  # View current builder configuration
  vastde builders inspect
```

## Subcommands

- [inspect](vastde_builders_inspect.md) - Inspect detailed information about a builder image tag
- [list](vastde_builders_list.md) - List available vast-builder images from Docker Hub
- [set](vastde_builders_set.md) - Set the builder image URL

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

