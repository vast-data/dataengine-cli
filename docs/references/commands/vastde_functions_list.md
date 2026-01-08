---
title: vastde functions list
description: List VAST DataEngine functions
---

# vastde functions list

List VAST DataEngine functions

## Synopsis

List all functions available in your VAST DataEngine environment.

This command displays all registered functions that can be invoked or used in triggers and pipelines.
Each entry shows the function name, GUID, image source, status, and key configuration details.

You can filter results by function name (--name) and control pagination (--limit, --cursor).
The output can be formatted as human-readable tables, JSON, or YAML for integration with
automation tools or further processing.

Functions must be in a published state to be invoked by triggers or used in pipelines. Use
this command to verify function availability and identify which functions are ready for use.

The list includes:
- Function name and unique identifier
- Container image and tag information
- Published and revision status
- Resource configuration
- Creation date

```
vastde functions list [flags]
```

## Examples

```bash
  # List all functions in your environment
  vastde functions list

  # List functions with a specific name
  vastde functions list --name image-processor

  # List functions with pagination (first 10 results)
  vastde functions list --limit 10

  # List functions starting from a specific cursor position
  vastde functions list --cursor <cursor-token>

  # List functions with JSON output for scripting
  vastde functions list --output json

  # List functions with YAML output
  vastde functions list --output yaml

  # Combine filters: limit results by name and format as JSON
  vastde functions list --name data-transformer --output json
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-l`, `--limit` | int32 | Maximum number of items to display (0 = no limit) | `0` |
| `-n`, `--name` | string | Filter by function name |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

