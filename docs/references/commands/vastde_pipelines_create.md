---
title: vastde pipelines create
description: Create a VAST DataEngine pipeline
---

# vastde pipelines create

Create a VAST DataEngine pipeline

## Synopsis

Create a VAST DataEngine pipeline

```
vastde pipelines create [flags]
```

## Examples

```bash
  # Create pipeline from YAML configuration file
  vastde pipelines create --config pipeline-config.yaml

  # Create pipeline from JSON file
  vastde pipelines create --config pipeline-config.json

  # Create pipeline from inline JSON string
  vastde pipelines create --config '{"name":"data-pipeline","steps":[...]}'

  # Create pipeline using @ syntax for file path
  vastde pipelines create --config @path/to/pipeline.yaml

  # Create pipeline with secrets from a file
  vastde pipelines create --config pipeline-config.yaml --secret-file secrets.yaml

  # Create pipeline with multiple secret files
  vastde pipelines create --config pipeline-config.yaml \
    --secret-file db-secrets.yaml \
    --secret-file api-secrets.yaml

  # Secret file format (secrets.yaml):
  #   name: my-database-credentials
  #   kubernetes_cluster_vrn: vast:dataengine:kubernetes-cluster:my-cluster
  #   namespace: default
  #   entries:
  #     - key: DB_HOST
  #       value: postgres.example.com
  #     - key: DB_USERNAME
  #       value: myuser
  #     - key: DB_PASSWORD
  #       value: super-secret-password

  # Create and immediately deploy the pipeline
  vastde pipelines create --config pipeline-config.yaml --deploy

  # Create pipeline with JSON output for automation
  vastde pipelines create --config pipeline-config.yaml --output json

  # Dry-run to preview the API request
  vastde pipelines create --config pipeline-config.yaml --dry-run
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--config` | string | Path to YAML/JSON config file, raw JSON string, or @path/to/file |  |
| `--deploy` | bool | Deploy the pipeline after creation |  |
| `--description` | string | A description of the resource. (optional) |  |
| `--name` | string | A name for the resource |  |
| `--secret-file` | stringSlice | Path to YAML/JSON file containing secrets to create and attach to pipeline (can be specified multiple times) |  |
| `--tags` | stringSlice | Custom tags to apply. (optional) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines

