---
title: vastde triggers list
description: List VAST DataEngine triggers
---

# vastde triggers list

List VAST DataEngine triggers

## Synopsis

List VAST DataEngine triggers

```
vastde triggers list [flags]
```

## Examples

```bash
  # List all triggers
  vastde triggers list

  # List triggers with pagination (first 10 results)
  vastde triggers list --limit 10

  # List triggers filtered by name
  vastde triggers list --name image-processor-trigger

  # List triggers filtered by type
  vastde triggers list --type Element

  # List triggers with cursor pagination
  vastde triggers list --cursor <cursor-token>

  # List triggers as JSON for automation
  vastde triggers list --output json

  # Combine filters: list Element triggers with limit
  vastde triggers list --type Element --limit 5 --output json
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-l`, `--limit` | int32 | Maximum number of items to display (0 = no limit) | `0` |
| `-n`, `--name` | string | Filter by trigger name |  |
| `-t`, `--type` | string | Filter by trigger type (Element|Schedule) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde triggers](vastde_triggers.md) - Manage VAST DataEngine triggers

