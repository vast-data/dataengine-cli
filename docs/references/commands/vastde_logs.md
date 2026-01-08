---
title: vastde logs
description: View VAST DataEngine logs
---

# vastde logs

View VAST DataEngine logs

## Synopsis

View and stream logs from VAST DataEngine functions and workloads.

The logs command group provides access to execution logs from your DataEngine functions and other
resources. Logs are essential for debugging, monitoring, and understanding the behavior of your
serverless applications.

You can retrieve historical logs using the 'get' command or stream live logs using the 'tail'
command. Logs can be filtered by resource type, name, time range, and other criteria. The CLI
supports multiple output formats including human-readable text, JSON, and YAML.

Logs include standard output (stdout) and standard error (stderr) from your functions, as well
as system logs from the DataEngine platform. Log entries include timestamps, log levels, and
contextual information about the execution environment.

## Subcommands

- [get](vastde_logs_get.md) - Show logs for a VAST DataEngine pipeline
- [tail](vastde_logs_tail.md) - Tail logs for a VAST DataEngine pipeline

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

