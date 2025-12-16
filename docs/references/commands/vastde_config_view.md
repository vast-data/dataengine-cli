---
title: vastde config view
description: View configuration values
---

# vastde config view

View configuration values

## Synopsis

Display current CLI configuration values.

This command shows all configuration values from ~/.vast/config.toml, including:

- Authentication credentials (tenant, username, password)
- Server URLs (VMS URL, builder image URL)
- Other CLI settings

The output can be formatted as human-readable text, JSON, or YAML (using the global
--output flag). Sensitive values like passwords are displayed, so use caution when
sharing output.

The displayed values represent what is stored in the configuration file. Note that
environment variables can override these values at runtime. To see the effective
values being used (including environment variable overrides), check the command
behavior or set the verbose flag.

Use this command to:
- Verify configuration after initialization or updates
- Check current authentication settings
- Debug configuration issues
- Export configuration for backup or sharing (excluding sensitive data)

```
vastde config view
```

## Examples

```bash
  # Display current configuration
  vastde config view

  # View configuration as JSON
  vastde config view --output json

  # View configuration as YAML
  vastde config view --output yaml

  # View configuration for scripting/automation
  vastde config view --output json | jq '.tenant'
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde config](vastde_config.md) - Manage CLI configuration

