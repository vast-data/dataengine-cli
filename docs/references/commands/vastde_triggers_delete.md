---
title: vastde triggers delete
description: Delete a VAST DataEngine trigger
---

# vastde triggers delete

Delete a VAST DataEngine trigger

## Synopsis

Delete a VAST DataEngine trigger

```
vastde triggers delete [guid|name] [flags]
```

## Examples

```bash
  # Delete trigger by name
  vastde triggers delete old-trigger

  # Delete trigger by GUID
  vastde triggers delete a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Delete with force flag (reserved for future enhancement)
  vastde triggers delete deprecated-trigger --force

  # Dry-run deletion to preview the operation
  vastde triggers delete test-trigger --dry-run
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

- [vastde triggers](vastde_triggers.md) - Manage VAST DataEngine triggers

