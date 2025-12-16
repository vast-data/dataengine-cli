---
title: vastde traces get
description: Get VAST DataEngine trace details
---

# vastde traces get

Get VAST DataEngine trace details

## Synopsis

Get VAST DataEngine trace details

```
vastde traces get [trace-id]
```

## Examples

```bash
  # Get trace details by trace ID
  vastde traces get abc123-def456-789xyz

  # Get trace details as JSON
  vastde traces get abc123-def456-789xyz --output json

  # Get trace details as YAML
  vastde traces get abc123-def456-789xyz --output yaml
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde traces](vastde_traces.md) - View VAST DataEngine traces

