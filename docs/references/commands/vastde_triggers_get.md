---
title: vastde triggers get
description: Get a VAST DataEngine trigger details
---

# vastde triggers get

Get a VAST DataEngine trigger details

## Synopsis

Get a VAST DataEngine trigger details

```
vastde triggers get [guid|name]
```

## Examples

```bash
  # Get trigger details by name
  vastde triggers get image-processor-trigger

  # Get trigger details by GUID
  vastde triggers get a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Get trigger details as JSON
  vastde triggers get my-trigger --output json

  # Get trigger details as YAML
  vastde triggers get my-trigger --output yaml

  # Extract specific field for scripting
  vastde triggers get my-trigger --output json | jq '.type'
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde triggers](vastde_triggers.md) - Manage VAST DataEngine triggers

