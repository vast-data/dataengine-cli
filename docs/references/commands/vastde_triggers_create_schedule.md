---
title: vastde triggers create schedule
description: Create a new schedule trigger
---

# vastde triggers create schedule

Create a new schedule trigger

## Synopsis

Create a new schedule trigger

```
vastde triggers create schedule [flags]
```

## Examples

```bash
  # Create a schedule trigger that runs every hour
  vastde triggers create schedule \
    --name hourly-job \
    --cron-schedule "0 * * * *"

  # Create a schedule trigger from YAML configuration file
  vastde triggers create schedule --from-file trigger-config.yaml

  # Create a schedule trigger that runs daily at midnight
  vastde triggers create schedule \
    --name daily-cleanup \
    --cron-schedule "0 0 * * *" \
    --description "Daily cleanup job"

  # Create a schedule trigger with broker configuration
  vastde triggers create schedule \
    --name kafka-scheduled-job \
    --cron-schedule "0 2 * * *" \
    --topic-name my-topic \
    --broker-type Internal \
    --broker-name my-broker

  # Create a schedule trigger with custom tags
  vastde triggers create schedule \
    --name tagged-job \
    --cron-schedule "0 6 * * *" \
    --tags "env:prod,team:data"
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-m`, `--broker-name` | string | The broker name for the trigger |  |
| `-b`, `--broker-type` | string | The broker type for the trigger |  |
| `-u`, `--broker-url` | string | The broker URL for the trigger |  |
| `--cron-schedule` | string | The cron schedule for the trigger |  |
| `--custom-extension` | stringArray | Custom extension as key=value or @file (repeatable, only flat key-value pairs allowed) |  |
| `--description` | string | A description of the resource. (optional) |  |
| `-f`, `--from-file` | string | Path to trigger config file (yaml|json) |  |
| `-n`, `--name` | string | A name for the resource |  |
| `--tags` | stringSlice | Custom tags to apply. (optional, comma-separated or repeated) |  |
| `-t`, `--topic-name` | string | The topic name for the trigger |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde triggers create](vastde_triggers_create.md) - Create a VAST DataEngine trigger

