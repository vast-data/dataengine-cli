---
title: vastde logs get
description: Show logs for a VAST DataEngine pipeline
---

# vastde logs get

Show logs for a VAST DataEngine pipeline

## Synopsis

Retrieve historical logs for a specific pipeline and its functions.

This command queries the DataEngine telemetry system to fetch execution logs for a pipeline
identified by its name or GUID. Logs provide detailed information about pipeline and function
execution, including:

- Function invocations and outputs
- Runtime errors and exceptions
- Custom log messages from function code
- System events and status messages

Filtering options:
- --function: Filter by specific function within the pipeline
- --since: Start time for log range (default: 5m ago)
- --end: End time for log range
- --severity: Filter by log level (TRACE, DEBUG, INFO, WARN, ERROR, CRITICAL)
- --scope: Filter by scope (user, runtime)
- --trace-id/--span-id: Filter by distributed trace identifiers
- --limit: Maximum number of log entries (default: 100)
- --order-by: Sort order (asc, desc)

Time formats support relative durations (5m, 2h, 1d) or absolute timestamps.
Logs are essential for debugging pipeline issues, monitoring execution, and understanding
system behavior.

```
vastde logs get [pipeline] [flags]
```

## Examples

```bash
  # Get logs for a pipeline
  vastde logs get data-processing-pipeline

  # Get logs filtered by severity level
  vastde logs get my-pipeline --severity ERROR

  # Get logs for a specific function in the pipeline
  vastde logs get my-pipeline --function image-processor

  # Get logs within a time range
  vastde logs get my-pipeline \
    --start "2024-01-01T00:00:00Z" \
    --end "2024-01-02T00:00:00Z"

  # Get logs with pagination
  vastde logs get my-pipeline --limit 100

  # Get logs filtered by trace ID for debugging
  vastde logs get my-pipeline --trace-id abc123-def456

  # Get logs as JSON for processing
  vastde logs get my-pipeline --output json

  # Get recent error logs sorted by time
  vastde logs get production-pipeline \
    --severity ERROR \
    --order-by timestamp \
    --limit 50
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-e`, `--end` | string | Filter logs until this end time (e.g. '5m', '2025-04-21T12:00:00Z') |  |
| `-f`, `--function` | string | Filter logs by function name or GUID |  |
| `-l`, `--limit` | int32 | Maximum number of log records to return | `100` |
| `--order-by` | string | Sort order for logs (asc, desc) |  |
| `--scope` | string | Filter logs by scope (user, runtime) |  |
| `--severity` | string | Filter logs by severity (TRACE, DEBUG, INFO, WARN, ERROR, CRITICAL) |  |
| `-s`, `--since` | string | Filter logs since this time ago (e.g. '10m', '2h', '2025-04-21T10:00:00Z'). Default is 5m. | `5m` |
| `--span-id` | string | Filter logs by span ID |  |
| `--trace-id` | string | Filter logs by trace ID |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde logs](vastde_logs.md) - View VAST DataEngine logs

