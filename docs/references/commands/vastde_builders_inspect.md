---
title: vastde builders inspect
description: Inspect detailed information about a builder image tag
---

# vastde builders inspect

Inspect detailed information about a builder image tag

## Synopsis

Inspect detailed information about a specific builder image tag from Docker Hub.

This command displays comprehensive information about a builder image tag from the
vastdataorg/vast-builder repository on Docker Hub, including:
  - Tag name and repository
  - Image size
  - Last updated timestamp
  - Image digest/SHA
  - Architecture and OS information
  - Multi-architecture support details

The output format is consistent across all tags, showing N/A for missing fields,
making it easy to compare different builder images.

If no tag is specified, the command displays the currently configured builder image.

```
vastde builders inspect [tag]
```

## Examples

```bash
  # Inspect details for a specific tag
  vastde builders inspect v1.0.60ee8cc7.vast-5.4

  # Display current builder image configuration
  vastde builders inspect
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde builders](vastde_builders.md) - View and select VAST DataEngine builder images

