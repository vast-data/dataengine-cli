---
title: vastde traces
description: View VAST DataEngine traces
---

# vastde traces

View VAST DataEngine traces

## Synopsis

View distributed traces from VAST DataEngine function executions and workflows.

Traces provide detailed visibility into the execution flow of your DataEngine applications.
Each trace represents a single execution path through your functions and pipelines, showing
timing information, spans, and the relationships between different components.

Traces are essential for:
- Performance analysis and optimization
- Understanding execution flow across multiple functions
- Debugging complex pipeline behaviors
- Identifying bottlenecks in data processing

Each trace consists of multiple spans representing individual operations. Traces can be
filtered by time range, function name, status, and other attributes. The CLI supports
exporting traces in multiple formats for analysis in external tools.

## Subcommands

- [get](vastde_traces_get.md) - Get VAST DataEngine trace details
- [list](vastde_traces_list.md) - List VAST DataEngine traces by filter

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

