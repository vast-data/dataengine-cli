---
title: vastde traces list
description: List VAST DataEngine traces by filter
---

# vastde traces list

List VAST DataEngine traces by filter

## Synopsis

List VAST DataEngine traces by filter

```
vastde traces list [pipeline] [flags]
```

## Examples

```bash
  # List traces for a pipeline
  vastde traces list data-processing-pipeline

  # List traces within a time range
  vastde traces list my-pipeline \
    --since "2024-01-01T00:00:00Z" \
    --end "2024-01-02T00:00:00Z"

  # List traces filtered by event type
  vastde traces list my-pipeline --event-type vastdata.com:Element.ObjectCreated

  # List traces filtered by status
  vastde traces list my-pipeline --status SUCCESS

  # List traces with pagination
  vastde traces list my-pipeline --limit 50

  # List traces sorted by time
  vastde traces list my-pipeline --order-by start_time

  # List traces as JSON for processing
  vastde traces list my-pipeline --output json

  # List recent traces (last 1 hour)
  vastde traces list my-pipeline --since 1h
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-e`, `--end` | string | Filter traces until this duration ago (e.g. '5m', '2025-04-21T12:00:00Z') |  |
| `-i`, `--event-id` | string | Filter traces by event ID |  |
| `-t`, `--event-type` | string | Filter traces by event type |  |
| `-l`, `--limit` | int32 | Maximum number of traces to return | `20` |
| `--order-by` | string | Sort order for traces (asc, desc) |  |
| `-s`, `--since` | string | Filter traces since this duration ago (e.g. '10m', '2h', '2025-04-21T10:00:00Z') | `1m` |
| `--status` | string | Filter traces by status (e.g. 'UNSET', 'OK', 'ERROR') |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde traces](vastde_traces.md) - View VAST DataEngine traces

