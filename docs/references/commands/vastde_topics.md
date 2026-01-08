---
title: vastde topics
description: Manage VAST DataEngine topics
---

# vastde topics

Manage VAST DataEngine topics

## Synopsis

View and manage Kafka topics used by VAST DataEngine for event streaming.

Topics are Kafka topics that serve as event streams for DataEngine functions and pipelines.
They act as message queues that decouple event producers from event consumers, enabling
asynchronous, scalable data processing.

Topics are created automatically by DataEngine when needed, such as when setting up the
default topic or dead letter topic during DataEngine setup. Functions and triggers can
publish events to topics, and pipelines can consume events from topics.

The topics command group provides read-only access to view topic configurations and
properties. Topic management operations (create, update, delete) are handled through
the Kafka broker configuration during DataEngine setup.

## Subcommands

- [get](vastde_topics_get.md) - Get a VAST DataEngine topic details
- [list](vastde_topics_list.md) - List VAST DataEngine topics

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

