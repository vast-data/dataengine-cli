---
title: vastde buckets get
description: Get details of a specific S3-enabled VMS view
---

# vastde buckets get

Get details of a specific S3-enabled VMS view

## Synopsis

Get detailed information about a specific S3-enabled VMS view (bucket).

This command retrieves comprehensive details about a single bucket identified by its S3 bucket name.
The bucket must be a VMS view with S3 protocol enabled. The command displays information including:

- Bucket (S3) name
- View name and ID
- File system path
- Enabled protocols
- Additional view metadata

Use this command to inspect bucket configuration and verify S3 access settings before using the
bucket in functions or pipelines.

```
vastde buckets get <bucket-name>
```

## Examples

```bash
  # Get bucket details
  vastde buckets get my-data-bucket

  # Get bucket details as JSON
  vastde buckets get production-bucket --output json

  # Get bucket details as YAML
  vastde buckets get staging-bucket --output yaml
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde buckets](vastde_buckets.md) - Manage VAST DataEngine buckets

