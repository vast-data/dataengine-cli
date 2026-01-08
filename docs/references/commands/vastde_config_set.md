---
title: vastde config set
description: Set configuration values
---

# vastde config set

Set configuration values

## Synopsis

Set or update configuration values in the CLI configuration file.

This command modifies one or more configuration values in ~/.vast/config.toml. You can
update the following settings:

- --tenant: VAST tenant name for authentication
- --username: VAST username for authentication
- --password: Access secret/password for authentication
- --vms-url: VAST VMS server URL (e.g., https://my-vms.example.com)
- --builder-image-url: VAST DataEngine builder image URL for function builds

Only the values you explicitly specify via flags will be updated; other configuration
values remain unchanged. This allows you to selectively update specific settings without
affecting other configuration.

The configuration file must already exist (use 'config init' to create it first). After
updating values, you can verify the changes using 'config view'.

Note: Configuration values can be overridden temporarily using environment variables
(VAST_TENANT, VAST_USERNAME, etc.) without modifying the configuration file.

```
vastde config set [flags]
```

## Examples

```bash
  # Set tenant name
  vastde config set --tenant my-production-tenant

  # Set multiple authentication values at once
  vastde config set --username admin --password secret123

  # Update VMS URL
  vastde config set --vms-url https://new-vms.example.com

  # Update builder image URL for function builds
  vastde config set \
    --builder-image-url vastdataorg/vast-builder:v1.0.latest

  # Set all configuration values in one command
  vastde config set \
    --tenant my-tenant \
    --username myuser \
    --password mypass \
    --vms-url https://vms.example.com \
    --builder-image-url vastdataorg/vast-builder:v1.0.60ee8cc7

  # Update only the password (keeping other values unchanged)
  vastde config set --password new-secure-password
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--builder-image-url` | string | Set VAST DataEngine builder image URL |  |
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

