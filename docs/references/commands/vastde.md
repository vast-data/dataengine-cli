---
title: vastde
description: VAST DataEngine CLI
---

# vastde

VAST DataEngine CLI

## Synopsis

The VAST DataEngine CLI (vastde) is a command-line interface for managing and interacting with VAST DataEngine resources.

VAST DataEngine is a serverless computing platform that enables you to build and deploy event-driven applications
using functions, pipelines, and triggers. The CLI provides comprehensive management capabilities for all DataEngine
entities including functions, pipelines, triggers, compute clusters, container registries, and more.

The CLI supports multiple output formats (human-readable, JSON, YAML) and includes features like dry-run mode
for safe operation testing, verbose logging for debugging, and integrated telemetry access for monitoring.

## Subcommands

- [buckets](vastde_buckets.md) - Manage VAST DataEngine buckets
- [builders](vastde_builders.md) - View and select VAST DataEngine builder images
- [completion](vastde_completion.md) - Generate the autocompletion script for the specified shell
- [compute-clusters](vastde_compute-clusters.md) - Manage VAST DataEngine compute clusters
- [config](vastde_config.md) - Manage CLI configuration
- [container-registries](vastde_container-registries.md) - Manage VAST DataEngine container registries
- [doc](vastde_doc.md) - Generate CLI documentation
- [functions](vastde_functions.md) - Manage VAST DataEngine functions
- [logs](vastde_logs.md) - View VAST DataEngine logs
- [metrics](vastde_metrics.md) - View VAST DataEngine metrics
- [pipelines](vastde_pipelines.md) - Manage VAST DataEngine pipelines
- [setup-dataengine](vastde_setup-dataengine.md) - Setup VAST DataEngine provisioning
- [topics](vastde_topics.md) - Manage VAST DataEngine topics
- [traces](vastde_traces.md) - View VAST DataEngine traces
- [triggers](vastde_triggers.md) - Manage VAST DataEngine triggers
- [version](vastde_version.md) - CLI version

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

