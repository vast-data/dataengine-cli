---
title: vastde topics get
description: Get a VAST DataEngine topic details
---

# vastde topics get

Get a VAST DataEngine topic details

## Synopsis

Get a VAST DataEngine topic details

## Usage

```
vastde topics get <GUID>|<name> [options]
```

## Examples

```bash
  # Get topic details by name (requires database name)
  vastde topics get my-topic --database-name kafka-view1

  # Get topic details by GUID
  vastde topics get 5de842e9-5be0-4eb3-bb4b-6c5b8ba84806

  # Get topic details as JSON
  vastde topics get event-stream --database-name kafka-db --output json

  # Get topic details as YAML
  vastde topics get notifications --database-name kafka-db --output yaml
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--database-name` | string | Database name (required for name-based lookup) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: `json`, `yaml`, `human` | `human` |
| `--silent` | bool | Suppress UI outputs, such as spinner and success messages |  |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde topics](vastde_topics.md) - Manage VAST DataEngine topics

