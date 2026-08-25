---
title: vastde triggers create element
description: Create a new element trigger
---

# vastde triggers create element

Create a new element trigger

## Synopsis

Create a new VAST DataEngine element trigger

## Usage

```
vastde triggers create element [options]
```

## Examples

```bash
  # Create Element trigger for object created events
  vastde triggers create element \
    --name image-processor-trigger \
    --event "ObjectCreated:*" \
    --source-bucket my-bucket

  # Create Element trigger from YAML configuration file
  vastde triggers create element --from-file trigger-config.yaml

  # Create Element trigger with name prefix filter
  vastde triggers create element \
    --name csv-processor-trigger \
    --event "ObjectCreated:*" \
    --source-bucket data-bucket \
    --name-prefix "csv/"

  # Create Element trigger with multiple events (using repeated flag)
  vastde triggers create element \
    --name multi-event-trigger \
    --event "ObjectCreated:*" \
    --event "ObjectRemoved:*" \
    --source-bucket my-bucket

  # Create Element trigger with broker configuration
  vastde triggers create element \
    --name kafka-trigger \
    --event "ObjectCreated:*" \
    --source-bucket my-bucket \
    --topic-name my-topic \
    --broker-type kafka \
    --broker-name my-broker

  # Create Element trigger with tag filters
  vastde triggers create element \
    --name tagged-trigger \
    --event "ObjectTagging:Put" \
    --source-bucket my-bucket \
    --tag-prefix "env:prod"
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-m`, `--broker-name` | string | The broker name for the trigger |  |
| `-b`, `--broker-type` | string | The broker type for the trigger |  |
| `-u`, `--broker-url` | string | The broker URL for the trigger |  |
| `--custom-extension` | stringArray | Custom extension as key=value or @file (repeatable, only flat key-value pairs allowed) |  |
| `--description` | string | A description of the resource. (optional) |  |
| `--event` | stringSlice | List of events (can be repeated). Allowed: ObjectCreated:*, ObjectRemoved:*, ObjectTagging:Put, ObjectTagging:Delete |  |
| `-f`, `--from-file` | string | Path to trigger config file (yaml|json) |  |
| `-n`, `--name` | string | A name for the resource |  |
| `--name-prefix` | string | Name filter prefix for element triggers |  |
| `--name-suffix` | string | Name filter suffix for element triggers |  |
| `-s`, `--source-bucket` | string | The source bucket name for the trigger |  |
| `--source-types` | stringSlice | The source types for the trigger (comma-separated or repeated) |  |
| `--tag-prefix` | string | Tag filter prefix for element triggers |  |
| `--tag-suffix` | string | Tag filter suffix for element triggers |  |
| `--tags` | stringSlice | Custom tags to apply. (optional, comma-separated or repeated) |  |
| `-t`, `--topic-name` | string | The topic name for the trigger |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: `json`, `yaml`, `human` | `human` |
| `--silent` | bool | Suppress UI outputs, such as spinner and success messages |  |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde triggers create](vastde_triggers_create.md) - Create a VAST DataEngine trigger

