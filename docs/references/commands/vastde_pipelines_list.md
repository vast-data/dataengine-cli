---
title: vastde pipelines list
description: List VAST DataEngine pipelines
---

# vastde pipelines list

List VAST DataEngine pipelines

## Synopsis

List VAST DataEngine pipelines

```
vastde pipelines list [flags]
```

## Examples

```bash
  # List all pipelines
  vastde pipelines list

  # List pipelines with pagination (first 10 results)
  vastde pipelines list --limit 10

  # List pipelines starting from a cursor position
  vastde pipelines list --cursor <cursor-token>

  # List pipelines with JSON output for automation
  vastde pipelines list --output json

  # List pipelines with YAML output
  vastde pipelines list --output yaml

  # Combine limit with JSON output
  vastde pipelines list --limit 5 --output json
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

- [vastde pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines

