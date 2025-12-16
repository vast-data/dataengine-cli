---
title: vastde config init
description: Initialize vastde config file
---

# vastde config init

Initialize vastde config file

## Synopsis

Initialize the VAST DataEngine CLI configuration file.

This command creates a new configuration file at ~/.vast/config.toml with default values
and any settings provided via command-line flags. The configuration file stores:

- Authentication credentials (tenant, username, password)
- Server URLs (VMS URL, builder image URL)
- CLI preferences and defaults

You should run this command before using other CLI commands for the first time. If a
configuration file already exists, the command will fail unless you use --force to
overwrite it.

The configuration file is created with restrictive permissions (0600) to protect sensitive
credentials. You can initialize with specific values using flags, or create an empty
configuration and set values later using 'config set'.

Example workflow:
1. vastde config init --tenant my-tenant --vms-url https://my-vms.example.com
2. vastde config set --username myuser --password mypass
3. Verify with: vastde config view

```
vastde config init [flags]
```

## Examples

```bash
  # Initialize config file with default values
  vastde config init

  # Initialize with tenant and VMS URL
  vastde config init --tenant my-company \
    --vms-url https://vms.example.com

  # Initialize with all authentication details
  vastde config init \
    --tenant my-tenant \
    --username myuser \
    --password mypassword \
    --vms-url https://vms.example.com

  # Initialize with builder image URL for function builds
  vastde config init \
    --tenant my-tenant \
    --vms-url https://vms.example.com \
    --builder-image-url vastdataorg/vast-builder:v1.0.60ee8cc7.vast-5.4

  # Force overwrite existing configuration
  vastde config init --force

  # Complete initialization with all options
  vastde config init \
    --tenant production-tenant \
    --username admin \
    --password secret123 \
    --vms-url https://prod-vms.example.com \
    --builder-image-url vastdataorg/vast-builder:latest \
    --force
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--builder-image-url` | string | Set VAST DataEngine builder image URL |  |
| `--force` | bool | Force overwrite of existing config file |  |
| `--password` | string | Set vast password |  |
| `--tenant` | string | Set vast tenant name |  |
| `--username` | string | Set vast username |  |
| `--vms-url` | string | Set vast VMS URL |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde config](vastde_config.md) - Manage CLI configuration

