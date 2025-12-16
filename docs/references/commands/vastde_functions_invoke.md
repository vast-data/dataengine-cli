---
title: vastde functions invoke
description: Send a cloudEvent to a local VAST DataEngine function
---

# vastde functions invoke

Send a cloudEvent to a local VAST DataEngine function

## Synopsis

Send a CloudEvent to a locally running or remote function for testing and invocation.

This command sends a CloudEvent to a function endpoint, triggering its execution. You can either:

1. Generate a test event automatically (--generate-event):
   Creates a default CloudEvent with standard VAST DataEngine format

2. Provide a custom event from a YAML file (--event):
   Load event data from a YAML file defining all CloudEvent fields

The CloudEvent format follows the CloudEvents specification and includes:
- id: Unique event identifier
- source: Event source URI
- type: Event type (e.g., vastdata.com:Element.ObjectCreated)
- data: Event payload (arbitrary JSON object)
- Additional metadata fields (time, subject, etc.)

Use --url to specify the function endpoint (defaults to http://localhost:8080/).
This is primarily used with 'functions localrun' for local testing, but can also invoke
remote function endpoints.

The command displays the function response and HTTP status code, making it easy to verify
function behavior during development and testing.

```
vastde functions invoke [flags]
```

## Examples

```bash
  # Generate and send a default test CloudEvent to local function
  vastde functions invoke --generate-event

  # Generate a CloudEvent with custom event type
  vastde functions invoke --generate-event \
    --event-type vastdata.com:Element.ObjectDeleted

  # Send a CloudEvent from YAML file to local function
  vastde functions invoke --event my-event.yaml

  # Invoke function at custom URL (e.g., different port or remote endpoint)
  vastde functions invoke --generate-event \
    --url http://localhost:9000/

  # Invoke remote deployed function endpoint
  vastde functions invoke --event test-event.yaml \
    --url https://my-function.example.com/invoke

  # Test function with realistic object created event
  vastde functions invoke --generate-event \
    --event-type vastdata.com:Element.ObjectCreated \
    --url http://localhost:8080/
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-e`, `--event` | string | Path to the CloudEvent YAML file |  |
| `-t`, `--event-type` | string | Type for generated CloudEvent | `vastdata.com:Element.ObjectCreated` |
| `-g`, `--generate-event` | bool | Generate a default CloudEvent automatically |  |
| `-u`, `--url` | string | URL of the locally running function | `http://localhost:8080/` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

