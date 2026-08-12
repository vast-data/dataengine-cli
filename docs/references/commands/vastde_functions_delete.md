---
title: vastde functions delete
description: Delete a VAST DataEngine function
---

# vastde functions delete

Delete a VAST DataEngine function

## Synopsis

Delete a function from VAST DataEngine.

This command removes a function identified by its GUID or name from DataEngine. After deletion,
the function can no longer be invoked or used in triggers and pipelines.

Important considerations:
- Any triggers or pipelines referencing this function will fail or become inactive
- You should update or remove dependent triggers and pipelines before deleting
- This operation only removes the function from DataEngine; the container image remains in the registry
- All function revisions and execution history will be removed
- The --force flag is available but currently does not skip confirmation (reserved for future enhancement)

Use this command when:
- Decommissioning functions that are no longer needed
- Cleaning up test or development functions
- Replacing functions with new implementations

The function's container image in the registry is not affected by deletion. You can recreate
the function later by using 'functions create' with the same image.

```
vastde functions delete [guid|name] [flags]
```

## Examples

```bash
  # Delete function by name
  vastde functions delete old-function

  # Delete function by GUID
  vastde functions delete a1b2c3d4-e5f6-7890-abcd-ef1234567890

  # Delete with force flag (reserved for future enhancement)
  vastde functions delete deprecated-function --force

  # Dry-run deletion to preview the operation
  vastde functions delete test-function --dry-run
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-f`, `--force` | bool | Skip confirmation prompt |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

