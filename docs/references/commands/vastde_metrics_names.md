---
title: vastde metrics names
description: List available metric names
---

# vastde metrics names

List available metric names

## Synopsis

List available metric names

```
vastde metrics names [flags]
```

## Examples

```bash
  # List all metric names
  vastde metrics names
  # List all metric names containing the string "my-metric"
  vastde metrics names --search "my-metric"
  # List all metric names for the pipeline "my-pipeline"
  vastde metrics names --pipeline "my-pipeline"
  # List all metric names for the function "my-function"
  vastde metrics names --function "my-function"
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-f`, `--function` | string | Filter metrics by function name |  |
| `-t`, `--metric-type` | string | Filter metrics by metric type (Counter, Histogram, Gauge, UpDownCounter) |  |
| `-p`, `--pipeline` | string | Filter metrics by pipeline name |  |
| `-s`, `--search` | string | Filter metrics by name containing this string (case-insensitive substring match) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde metrics](vastde_metrics.md) - View VAST DataEngine metrics

