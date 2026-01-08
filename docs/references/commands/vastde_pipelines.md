---
title: vastde pipelines
description: Manage VAST DataEngine pipelines
---

# vastde pipelines

Manage VAST DataEngine pipelines

## Synopsis

Manage VAST DataEngine pipelines for orchestrating data processing workflows.

Pipelines are declarative workflows that define how data flows through your DataEngine
application. A pipeline consists of multiple stages, each executing a function to transform,
process, or route data. Pipelines enable you to build complex data processing workflows by
chaining functions together.

Key concepts:
- Stages: Individual steps in the pipeline, each referencing a function
- Data Flow: How data moves from one stage to the next
- Error Handling: Dead letter queues and retry policies for failed stages
- Deployment: Pipelines must be deployed to become active

Pipelines can be defined in YAML configuration files that specify the stages, functions,
and data flow. The deploy command activates a pipeline and begins processing data. Pipelines
can be updated to modify the workflow without recreating them.

## Subcommands

- [create](vastde_pipelines_create.md) - Create a VAST DataEngine pipeline
- [delete](vastde_pipelines_delete.md) - Delete a VAST DataEngine pipline
- [deploy](vastde_pipelines_deploy.md) - Deploy a pipeline to kubernetes
- [get](vastde_pipelines_get.md) - Get a VAST DataEngine pipeline details or manifest
- [list](vastde_pipelines_list.md) - List VAST DataEngine pipelines
- [update](vastde_pipelines_update.md) - Update a VAST DataEngine pipeline

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

