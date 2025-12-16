---
title: vastde buckets
description: Manage VAST DataEngine buckets
---

# vastde buckets

Manage VAST DataEngine buckets

## Synopsis

Manage and view S3-enabled VMS views (buckets) in your VAST DataEngine environment.

In VAST DataEngine, buckets are VMS views with S3 protocol enabled. These views provide S3-compatible
object storage access to your data. The buckets command group allows you to list and inspect S3-enabled
views to understand your storage configuration.

Buckets are used by DataEngine functions and pipelines to access and store data, and are often configured
as sources or sinks for data processing workflows.

## Subcommands

- [get](vastde_buckets_get.md) - Get details of a specific S3-enabled VMS view
- [list](vastde_buckets_list.md) - List S3-enabled VMS views

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

