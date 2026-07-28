---
title: vastde pipelines get
description: Get a VAST DataEngine pipeline details or manifest
---

# vastde pipelines get

Get a VAST DataEngine pipeline details or manifest

## Synopsis

Get a VAST DataEngine pipeline details or manifest

```
vastde pipelines get [guid|name] [flags]
```

## Examples

```bash
  # Get pipeline details by name
  vastde pipelines get data-processing-pipeline

  # Get pipeline details by GUID
  vastde pipelines get a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Get pipeline details with JSON output
  vastde pipelines get data-pipeline --output json

  # Get full pipeline manifest (includes envs, secrets, deployments)
  vastde pipelines get data-pipeline --manifest

  # Get the deployed revision manifest
  vastde pipelines get data-pipeline --deployed

  # Get manifest as YAML for inspection
  vastde pipelines get ml-pipeline --manifest --output yaml
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--deployed` | bool | Return the deployed revision manifest instead of the latest revision (automatically enables --manifest) |  |
| `--manifest` | bool | Return the full pipeline manifest (envs, secrets, function deployments, links, etc.) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines

