---
title: vastde pipelines update
description: Update a VAST DataEngine pipeline
---

# vastde pipelines update

Update a VAST DataEngine pipeline

## Synopsis

Update a VAST DataEngine pipeline

```
vastde pipelines update [guid|name] [flags]
```

## Examples

```bash
  # Update pipeline from YAML configuration file
  vastde pipelines update data-pipeline --config updated-pipeline.yaml

  # Update pipeline from JSON file
  vastde pipelines update data-pipeline --config updated-config.json

  # Update pipeline using inline JSON
  vastde pipelines update data-pipeline --config '{"steps":[...]}'

  # Update pipeline by GUID
  vastde pipelines update a1b2c3d4-e5f6-7890-abcd-ef1234567890 \
    --config new-config.yaml

  # Update with @ file syntax
  vastde pipelines update ml-pipeline --config @path/to/config.yaml

  # Update pipeline and add secrets from a file
  vastde pipelines update data-pipeline \
    --config updated-config.yaml \
    --secret-file secrets.yaml

  # Update pipeline with multiple secret files
  vastde pipelines update data-pipeline \
    --config updated-config.yaml \
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

  # Dry-run to preview changes
  vastde pipelines update data-pipeline \
    --config updated-config.yaml \
    --dry-run

  # Update and output as JSON
  vastde pipelines update data-pipeline \
    --config updated-config.yaml \
    --output json
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--config` | string | Pipeline config as JSON string or @path/to/file.yaml|json |  |
| `--secret-file` | stringSlice | Path to YAML/JSON file containing secrets to create and attach to pipeline (can be specified multiple times) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines

