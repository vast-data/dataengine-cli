---
title: vastde triggers create
description: Create a VAST DataEngine trigger
---

# vastde triggers create

Create a VAST DataEngine trigger

## Synopsis

Create a VAST DataEngine trigger

```
vastde triggers create [command] [flags]
```

## Examples

```bash
  # Create Element trigger for object created events
  vastde triggers create \
    --name image-processor-trigger \
    --type Element \
    --events vastdata.com:Element.ObjectCreated \
    --source-bucket my-bucket

  # Create trigger from YAML configuration file
  vastde triggers create --from-file trigger-config.yaml

  # Create Element trigger with name prefix filter
  vastde triggers create \
    --name csv-processor-trigger \
    --type Element \
    --events vastdata.com:Element.ObjectCreated \
    --source-bucket data-bucket \
    --name-prefix "csv/"

  # Create trigger with multiple events
  vastde triggers create \
    --name multi-event-trigger \
    --type Element \
    --events "vastdata.com:Element.ObjectCreated,vastdata.com:Element.ObjectDeleted" \
    --source-bucket my-bucket

  # Create Cron trigger for scheduled execution
  vastde triggers create \
    --name daily-report-trigger \
    --type Cron \
    --cron-schedule "0 2 * * *"

  # Create trigger with custom extensions
  vastde triggers create \
    --name advanced-trigger \
    --type Element \
    --events vastdata.com:Element.ObjectCreated \
    --source-bucket my-bucket \
    --custom-extension "key1=value1" \
    --custom-extension "key2=value2"

  # Dry-run to preview the API request
  vastde triggers create \
    --name test-trigger \
    --type Element \
    --events vastdata.com:Element.ObjectCreated \
    --source-bucket test-bucket \
    --dry-run
```

## Subcommands

- [element](vastde_triggers_create_element.md) - Create a new element trigger
- [schedule](vastde_triggers_create_schedule.md) - Create a new schedule trigger

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--broker-name` | string | Broker name for external or Bucket (View) name for internal |  |
| `--broker-type` | string | Broker type (External or Internal) |  |
| `--broker-url` | string | URL to the broker (for External brokers) |  |
| `--cron-schedule` | string | Cron schedule for schedule triggers (required for --type schedule) |  |
| `--custom-extension` | stringArray | Custom extension as key=value or @file (repeatable, only flat key-value pairs allowed) |  |
| `--description` | string | A description of the resource. (optional) |  |
| `--events` | stringSlice | List of events (comma-separated or repeated, required for element triggers) |  |
| `-f`, `--from-file` | string | Path to trigger config file (yaml|json) |  |
| `-n`, `--name` | string | A name for the resource |  |
| `--name-prefix` | string | Name filter prefix for element triggers |  |
| `--name-suffix` | string | Name filter suffix for element triggers |  |
| `--source-bucket` | string | The source bucket name (required for element triggers). Use 'vastde buckets list' to see available buckets |  |
| `--tag-prefix` | string | Tag filter prefix for element triggers |  |
| `--tag-suffix` | string | Tag filter suffix for element triggers |  |
| `--tags` | stringSlice | Custom tags to apply. (optional) |  |
| `--topic` | string | Target topic for trigger events |  |
| `-t`, `--type` | string | The trigger type (Element,Schedule) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde triggers](vastde_triggers.md) - Manage VAST DataEngine triggers

