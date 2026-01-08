---
title: vastde triggers
description: Manage VAST DataEngine triggers
---

# vastde triggers

Manage VAST DataEngine triggers

## Synopsis

Manage triggers that activate DataEngine functions in response to events.

Triggers are event sources that invoke functions when specific conditions are met. They connect
external event sources to your functions, enabling event-driven architectures. DataEngine supports
multiple trigger types including:

- S3 triggers: Invoke functions when objects are created, modified, or deleted in S3 buckets
- HTTP triggers: Invoke functions via HTTP requests
- Schedule triggers: Invoke functions on a time-based schedule (cron)
- Topic triggers: Invoke functions when messages arrive on Kafka topics

Each trigger is associated with a specific function and defines the event pattern that activates
the function. Triggers can include filters to control which events actually invoke the function,
and can pass event data to the function as input parameters.

Triggers enable building reactive applications that respond automatically to data changes,
user actions, or scheduled operations.

## Subcommands

- [create](vastde_triggers_create.md) - Create a VAST DataEngine trigger
- [delete](vastde_triggers_delete.md) - Delete a VAST DataEngine trigger
- [get](vastde_triggers_get.md) - Get a VAST DataEngine trigger details
- [list](vastde_triggers_list.md) - List VAST DataEngine triggers
- [update](vastde_triggers_update.md) - Update a VAST DataEngine trigger

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

