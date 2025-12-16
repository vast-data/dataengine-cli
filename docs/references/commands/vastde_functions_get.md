---
title: vastde functions get
description: Get a VAST DataEngine function details
---

# vastde functions get

Get a VAST DataEngine function details

## Synopsis

Get detailed information about a specific function.

This command retrieves comprehensive details about a single function identified by either its
GUID or name. The function details include:

- Function name and GUID
- Container image source and registry
- Architecture and runtime configuration
- Published status and revision information
- Resource limits and scaling settings
- Associated tags and metadata
- Creation and modification timestamps

Use --with-revisions to include detailed revision history, showing all versions of the function
and their configurations. This is useful for understanding function evolution and comparing
revisions.

Use this command to:
- Verify function configuration before invocation
- Check which image version is currently deployed
- Inspect resource limits and scaling settings
- Review revision history and changes

```
vastde functions get [guid|name] [flags]
```

## Examples

```bash
  # Get function details by name
  vastde functions get image-processor

  # Get function details by GUID
  vastde functions get a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Get function with revision history
  vastde functions get data-transformer --with-revisions

  # Get function details as JSON
  vastde functions get ml-inference --output json

  # Get function with revisions as YAML
  vastde functions get event-handler --with-revisions --output yaml

  # Get function for scripting (extract specific field)
  vastde functions get my-function --output json | jq '.image_tag'
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-r`, `--with-revisions` | bool | Include revision information |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

