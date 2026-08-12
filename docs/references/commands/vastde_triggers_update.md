---
title: vastde triggers update
description: Update a VAST DataEngine trigger
---

# vastde triggers update

Update a VAST DataEngine trigger

## Synopsis

Update a VAST DataEngine trigger

```
vastde triggers update [guid|name] [flags]
```

## Examples

```bash
  # Update trigger description
  vastde triggers update my-trigger --description "Updated description"

  # Update trigger events
  vastde triggers update image-trigger \
    --events "vastdata.com:Element.ObjectCreated,vastdata.com:Element.ObjectModified"

  # Update Element trigger filters
  vastde triggers update csv-trigger \
    --name-prefix "processed/" \
    --name-suffix ".csv"

  # Update trigger from YAML file
  vastde triggers update my-trigger --from-file updated-config.yaml

  # Update Cron schedule
  vastde triggers update daily-job --cron-schedule "0 3 * * *"

  # Update by GUID
  vastde triggers update a1b2c3d4-e5f6-7890-abcd-ef1234567890 \
    --description "New description"

  # Dry-run update to preview changes
  vastde triggers update my-trigger \
    --description "Test update" \
    --dry-run
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--broker-name` | string | Update broker name for external or Kafka View name for internal |  |
| `--broker-type` | string | Update broker type (External or Internal) |  |
| `--broker-url` | string | Update URL to the broker (for External brokers) |  |
| `--cron-schedule` | string | Update cron schedule (Schedule triggers) |  |
| `--custom-extension` | stringArray | Update custom extensions |  |
| `--description` | string | Update trigger description |  |
| `--events` | stringSlice | Update events list (Element triggers) |  |
| `-f`, `--from-file` | string | Path to trigger update config file |  |
| `--name-prefix` | string | Update name filter prefix |  |
| `--name-suffix` | string | Update name filter suffix |  |
| `--source-bucket` | string | Update source bucket (Element triggers). Use 'vastde buckets list' to see available buckets |  |
| `--tag-prefix` | string | Update tag filter prefix |  |
| `--tag-suffix` | string | Update tag filter suffix |  |
| `--tags` | stringSlice | Update trigger tags |  |
| `--topic` | string | Update target topic |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde triggers](vastde_triggers.md) - Manage VAST DataEngine triggers

