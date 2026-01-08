---
title: vastde builders list
description: List available vast-builder images from Docker Hub
---

# vastde builders list

List available vast-builder images from Docker Hub

## Synopsis

List available vast-builder image tags from Docker Hub.

This command fetches the latest available builder image tags from the
vastdataorg/vast-builder repository on Docker Hub, including metadata
such as image size and last updated date.

```
vastde builders list [flags]
```

## Examples

```bash
  # List the latest 25 builder images
  vastde builders list

  # List the latest 50 builder images
  vastde builders list --page-size 50

  # List builder images in JSON format
  vastde builders list --output-format json

  # List builder images in YAML format
  vastde builders list -o yaml
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--page-size` | int | Number of tags to display | `25` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde builders](vastde_builders.md) - View and select VAST DataEngine builder images

