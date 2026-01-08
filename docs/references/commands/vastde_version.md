---
title: vastde version
description: CLI version
---

# vastde version

CLI version

## Synopsis

CLI version

```
vastde version
```

## Examples

```bash
  # Display CLI version
  vastde version

  # Use in scripts
  VERSION=$(vastde version)
  echo "Running CLI version: $VERSION"
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

