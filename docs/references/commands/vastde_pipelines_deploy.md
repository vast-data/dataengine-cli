---
title: vastde pipelines deploy
description: Deploy a pipeline to kubernetes
---

# vastde pipelines deploy

Deploy a pipeline to kubernetes

## Synopsis

Deploy a pipeline to kubernetes

```
vastde pipelines deploy [id]
```

## Examples

```bash
  # Deploy pipeline by name
  vastde pipelines deploy data-processing-pipeline

  # Deploy pipeline by GUID
  vastde pipelines deploy a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Dry-run deployment to preview the operation
  vastde pipelines deploy ml-inference-pipeline --dry-run
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines

