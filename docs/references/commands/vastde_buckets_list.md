---
title: vastde buckets list
description: List S3-enabled VMS views
---

# vastde buckets list

List S3-enabled VMS views

## Synopsis

List all S3-enabled VMS views (buckets) available in your VAST DataEngine environment.

This command displays all VMS views that have S3 protocol enabled, making them accessible as
S3 buckets. Each entry shows the bucket name, view details, and configuration. Only views with
active S3 protocol support are included in the results.

You can filter the results by bucket name and limit the number of entries returned. The output
can be formatted as human-readable tables, JSON, or YAML for programmatic processing.

S3-enabled views serve as data sources and sinks for DataEngine functions and pipelines, providing
S3-compatible object storage access to your VAST data.

```
vastde buckets list [flags]
```

## Examples

```bash
  # List all S3-enabled buckets
  vastde buckets list

  # List buckets with pagination
  vastde buckets list --limit 10

  # List buckets filtered by name
  vastde buckets list --name my-data-bucket

  # List buckets as JSON
  vastde buckets list --output json

  # List buckets with cursor pagination
  vastde buckets list --cursor <cursor-token>
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-l`, `--limit` | int32 | Maximum number of items to display (0 = no limit) | `0` |
| `-n`, `--name` | string | Filter by bucket name |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde buckets](vastde_buckets.md) - Manage VAST DataEngine buckets

