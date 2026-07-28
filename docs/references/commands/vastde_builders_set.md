---
title: vastde builders set
description: Set the builder image URL
---

# vastde builders set

Set the builder image URL

## Synopsis

Set the builder image URL configuration.

This command updates the builder image URL in the CLI configuration file.

If you provide just a tag (without repository), it will automatically use
the default VAST repository: vastdataorg/vast-builder

If you provide a full image path (containing '/'), it will be used as-is.

This is equivalent to running: vastde config set --builder-image-url <image-url>

```
vastde builders set <image-url|tag>
```

## Examples

```bash
  # Set using just a tag (uses default repository)
  vastde builders set v1.0.60ee8cc7.vast-5.4
  # Results in: vastdataorg/vast-builder:v1.0.60ee8cc7.vast-5.4

  # Set using full image path
  vastde builders set vastdataorg/vast-builder:v1.0.60ee8cc7.vast-5.4

  # Set using different registry
  vastde builders set myregistry.io/custom/builder:latest
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

