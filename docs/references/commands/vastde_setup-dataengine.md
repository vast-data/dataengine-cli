---
title: vastde setup-dataengine
description: Setup VAST DataEngine provisioning
---

# vastde setup-dataengine

Setup VAST DataEngine provisioning

## Synopsis

Setup data engine provisioning with Kafka broker configuration and topic names.

This command configures the data engine with:
- Kafka broker settings (External or Internal)
- Default topic name for data processing
- Dead letter topic name for failed messages
- Optional VIP pools for telemetries collector

The command supports both command-line flags and YAML configuration files.

```
vastde setup-dataengine [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--broker-name` | string | Broker name for external or Bucket (View) name for internal (required) |  |
| `--broker-type` | string | Broker type: External or Internal (required) |  |
| `--broker-url` | string | URL to the broker (for external brokers) |  |
| `--dead-letter-topic` | string | The name of the dead letter topic (required) |  |
| `--default-topic` | string | The name of the default topic (required) |  |
| `-f`, `--file` | string | Path to YAML file containing setup configuration |  |
| `--vip-pools` | intSlice | VIP Pools to use for the telemetries collector |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

