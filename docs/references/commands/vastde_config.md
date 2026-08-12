---
title: vastde config
description: Manage CLI configuration
---

# vastde config

Manage CLI configuration

## Synopsis

Manage CLI configuration settings for authentication and server connections.

The config command group manages the CLI configuration file located at ~/.vast/config.toml.
This file stores essential settings including:

- Authentication credentials (tenant, username, password, token)
- Server URLs (VMS URL, builder image URL)
- Default settings for CLI operations

Configuration values can be set via command-line flags or environment variables. Environment
variables take precedence over config file values, allowing temporary overrides without
modifying the configuration file.

Before using other CLI commands, you should initialize the configuration using 'config init'
and set your authentication credentials and server URLs.

## Subcommands

- [init](vastde_config_init.md) - Initialize vastde config file
- [set](vastde_config_set.md) - Set configuration values
- [unset](vastde_config_unset.md) - Unset configuration values
- [view](vastde_config_view.md) - View configuration values

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

