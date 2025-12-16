---
title: vastde functions
description: Manage VAST DataEngine functions
---

# vastde functions

Manage VAST DataEngine functions

## Synopsis

Manage VAST DataEngine functions for serverless code execution.

Functions are the core building blocks of DataEngine applications. A function is a container-based
unit of execution that processes events and data. Functions are triggered by events from triggers,
pipelines, or direct invocations, and can be written in any language that runs in a container.

The function lifecycle includes:
1. Initialize a function project with scaffolding (init)
2. Build the function container image locally (build)
3. Create the function in DataEngine (create)
4. Invoke the function to execute it (invoke)
5. Update the function configuration or code (update)

Functions support versioning through revisions, allowing you to maintain multiple versions and
roll back if needed. Each function can have environment variables, resource limits, and scaling
configurations. Functions can be tested locally before deployment using the localrun command.

## Subcommands

- [build](vastde_functions_build.md) - Build a VAST DataEngine function locally
- [create](vastde_functions_create.md) - Create a VAST DataEngine function
- [delete](vastde_functions_delete.md) - Delete a VAST DataEngine function
- [get](vastde_functions_get.md) - Get a VAST DataEngine function details
- [init](vastde_functions_init.md) - Generate a VAST DataEngine function scaffold
- [invoke](vastde_functions_invoke.md) - Send a cloudEvent to a local VAST DataEngine function
- [list](vastde_functions_list.md) - List VAST DataEngine functions
- [localrun](vastde_functions_localrun.md) - Run a built VAST DataEngine function as a local container
- [update](vastde_functions_update.md) - Update a VAST DataEngine function

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

