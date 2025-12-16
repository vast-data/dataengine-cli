---
title: vastde metrics get
description: Get VAST DataEngine metrics
---

# vastde metrics get

Get VAST DataEngine metrics

## Synopsis

Get VAST DataEngine metrics

```
vastde metrics get [flags]
```

## Examples

```bash
  # Get a single metric
  vastde metrics get --metric-names dataengine.function.invocations
  # Get multiple metrics (comma-separated)
  vastde metrics get --metric-names dataengine.function.invocations,dataengine.function.errors
  # Get metrics with a specific aggregation method
  vastde metrics get --metric-names dataengine.function.invocations --aggregation sum
  # Filter metrics by pipeline
  vastde metrics get --metric-names dataengine.function.invocations --pipeline my-pipeline
  # Filter metrics by function
  vastde metrics get --metric-names dataengine.function.invocations --function my-function
  # Group metrics by function name
  vastde metrics get --metric-names dataengine.function.invocations --group-by function_name
  # Get top 5 functions by metric value
  vastde metrics get --metric-names dataengine.function.invocations --group-by function_name --top-k 5
  # Get bottom 3 pipelines by metric value
  vastde metrics get --metric-names dataengine.function.invocations --group-by pipeline_name --bottom-k 3
  # Get metrics for the last 30 minutes
  vastde metrics get --metric-names dataengine.function.invocations --timeframe 30m
  # Get metrics for a specific time range
  vastde metrics get --metric-names dataengine.function.invocations --start-time 2024-01-01T00:00:00Z --end-time 2024-01-01T12:00:00Z
  # Limit the number of data points returned
  vastde metrics get --metric-names dataengine.function.invocations --max-points 30
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-a`, `--aggregation` | string | Aggregation method (sum, avg, min, max, p50, p95, p99), defaults to 'avg' |  |
| `-b`, `--bottom-k` | int | Return only the bottom K groups with lowest values (requires group-by, mutually exclusive with top-k) | `0` |
| `-e`, `--end-time` | string | End time (ISO 3339/8601 format, e.g. 2021-01-01T00:00:00Z), mutually exclusive with timeframe |  |
| `-f`, `--function` | string | Function name filter, optional |  |
| `-g`, `--group-by` | string | Group metrics by dimension (function_name, pipeline_name), optional |  |
| `-n`, `--max-points` | int | Maximum data points to return (1-100, defaults to 60) | `0` |
| `-m`, `--metric-names` | string | Comma-separated list of metric names (1-10 metrics, e.g. "http_requests,memory_usage,dataengine.function.invocations"). Allows alphanumeric characters, dots, colons, and underscores. |  |
| `-t`, `--metric-type` | string | Filter by metric type (Counter, Histogram, Gauge, UpDownCounter), optional |  |
| `-p`, `--pipeline` | string | Pipeline name filter, optional |  |
| `-s`, `--start-time` | string | Start time (ISO 3339/8601 format, e.g. 2021-01-01T00:00:00Z), mutually exclusive with timeframe |  |
| `-w`, `--timeframe` | string | Time window (e.g. 30s, 5m, 1h, 7d, defaults to 1h), mutually exclusive with start-time and end-time |  |
| `-k`, `--top-k` | int | Return only the top K groups with highest values (requires group-by, mutually exclusive with bottom-k) | `0` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde metrics](vastde_metrics.md) - View VAST DataEngine metrics

