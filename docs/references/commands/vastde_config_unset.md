---
title: vastde config unset
description: Unset configuration values
---

# vastde config unset

Unset configuration values

## Synopsis

Clear (unset) configuration values in the CLI configuration file.

This command removes configuration values from ~/.vast/config.toml by setting them to
empty strings. You can clear the following settings:

- --tenant: Clear tenant name
- --username: Clear username
- --password: Clear password
- --vms-url: Clear VMS server URL
- --builder-image-url: Clear builder image URL

Use this command when you want to remove sensitive credentials, switch contexts, or
reset configuration values to defaults. Unlike 'config set', which updates values,
'config unset' completely clears them.

You can specify multiple flags to clear multiple values in a single command. The
configuration file must already exist. After clearing values, you can verify the
changes using 'config view'.

This is particularly useful for:
- Removing credentials when switching between tenants
- Clearing sensitive data from the configuration
- Resetting configuration to use environment variable overrides

```
vastde config unset [flags]
```

## Examples

```bash
  # Clear password from configuration
  vastde config unset --password

  # Clear tenant and username
  vastde config unset --tenant --username

  # Clear all authentication credentials
  vastde config unset --tenant --username --password

  # Clear VMS URL to use environment variable instead
  vastde config unset --vms-url

  # Clear builder image URL
  vastde config unset --builder-image-url

  # Clear all configuration values
  vastde config unset \
    --tenant \
    --username \
    --password \
    --vms-url \
    --builder-image-url
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--builder-image-url` | bool | Unset builder image URL |  |
| `--password` | bool | Unset password |  |
| `--tenant` | bool | Unset tenant name |  |
| `--username` | bool | Unset username |  |
| `--vms-url` | bool | Unset VMS URL |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde config](vastde_config.md) - Manage CLI configuration

