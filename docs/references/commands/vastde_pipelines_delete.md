---
title: vastde pipelines delete
description: Delete a VAST DataEngine pipline
---

# vastde pipelines delete

Delete a VAST DataEngine pipline

## Synopsis

Delete a VAST DataEngine pipline

```
vastde pipelines delete [id]
```

## Examples

```bash
  # Delete pipeline by name
  vastde pipelines delete data-processing-pipeline

  # Delete pipeline by GUID
  vastde pipelines delete a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Dry-run deletion to preview the operation
  vastde pipelines delete old-pipeline --dry-run
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines

