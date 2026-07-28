---
title: vastde functions build
description: Build a VAST DataEngine function locally
---

# vastde functions build

Build a VAST DataEngine function locally

## Synopsis

Build a DataEngine function container image locally using Docker.

This command packages your function code into a container image using the VAST DataEngine
builder. The build process:

1. Validates the handler file (must contain init() and handler() functions)
2. Packages dependencies specified in requirements.txt
3. Creates a container image with the function runtime
4. Tags the image with the specified tag

Prerequisites:
- Docker must be installed and running
- Builder image URL must be configured (use 'config set --builder-image-url')
- Function code must have valid init() and handler() functions

The build process creates a build.log file in the target directory with detailed build output.
This log is useful for debugging build failures or understanding the build process.

Build options:
- --target: Function project directory (default: current directory)
- --handlers: Handler file name (default: main.py)
- --image-tag: Tag for the built image (default: latest)
- --pull-policy: Builder image pull policy (never|always|ifnotpresent)

After building, you can:
- Test locally using 'functions localrun'
- Push to a container registry
- Deploy to DataEngine using 'functions create'

```
vastde functions build [name] [flags]
```

## Examples

```bash
  # Build function with default settings (uses current directory)
  vastde functions build my-function

  # Build function from specific directory
  vastde functions build my-function --target ./my-function-code

  # Build with custom handler file name
  vastde functions build my-function \
    --target ./src \
    --handlers handler.py

  # Build with specific image tag
  vastde functions build image-processor --image-tag v1.2.3

  # Build with always pull policy for builder image
  vastde functions build my-function --pull-policy always

  # Build and verify output in build.log
  vastde functions build data-transformer --target ./transformer

  # Build for production with specific tag
  vastde functions build ml-model \
    --target ./ml-service \
    --image-tag production-v2.0.0
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-H`, `--handlers` | string | The Name of the handlers file (default is main.py) | `main.py` |
| `-T`, `--image-tag` | string | image Tag to apply | `latest` |
| `-P`, `--pull-policy` | string | Builder image pull policy [never|always|ifnotpresent] | `ifnotpresent` |
| `-t`, `--target` | string | The function target folder (default is current directory) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

