---
title: vastde topics list
description: List VAST DataEngine topics
---

# vastde topics list

List VAST DataEngine topics

## Synopsis

List VAST DataEngine topics

```
vastde topics list [flags]
```

## Examples

```bash
  # List topics in a database (database name required)
  vastde topics list --database-name kafka-view1

  # List topics with pagination
  vastde topics list --database-name kafka-db --limit 10

  # List topics filtered by name
  vastde topics list --database-name kafka-db --name event-stream

  # List topics as JSON
  vastde topics list --database-name kafka-db --output json

  # List topics with cursor pagination
  vastde topics list --database-name kafka-db --cursor <cursor-token>
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--database-name` | string | Database name (required) |  |
| `-l`, `--limit` | int32 | Maximum number of items to display (0 = no limit) | `0` |
| `-n`, `--name` | string | Filter by topic name |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde topics](vastde_topics.md) - Manage VAST DataEngine topics

