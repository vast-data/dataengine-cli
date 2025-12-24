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

1. Detects the programming language (Python, Go, Node.js) from project files
2. Validates the handler file based on language requirements
3. Validates the runtime version (e.g., Python version)
4. Packages dependencies (requirements.txt, go.mod, package.json)
5. Creates a container image with the function runtime
6. Tags the image with the specified tag

Language Detection:
The CLI automatically detects your function's language:
- Python: detected by presence of requirements.txt
- Go: detected by presence of go.mod (coming soon)
- Node.js: detected by presence of package.json (coming soon)

Prerequisites:
- Docker must be installed and running
- Builder image URL must be configured (use 'builders set')
- Function code must have valid handler file for the detected language

Python Functions:
- Handler file must contain init(ctx) and handler(ctx, event) functions
- Use --version to specify exact version (e.g., 3.12.11) or pattern (e.g., 3.12.*)
- Available versions are validated against the configured builder image

Build Output:
The build process creates a build.log file in the target directory with detailed build output.
This log is useful for debugging build failures or understanding the build process.

Cache Behavior:
The build process automatically caches runtime installations and dependencies for faster builds.
For Python functions, when you change the Python version, the cache is automatically cleared.
You can manually clear the cache using --clear-cache if you encounter issues.

After building, you can:
- Test locally using 'functions localrun'
- Push to a container registry (if --push was not set)
- Deploy to DataEngine using 'functions create'

```
vastde functions build <name> [flags]
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

  # Build Python function with specific version
  vastde functions build my-function --version 3.11.*

  # Build and verify output in build.log
  vastde functions build data-transformer --target ./transformer

  # Build for production with specific tag and Python version
  vastde functions build ml-model \
    --target ./ml-service \
    --image-tag production-v2.0.0 \
    --version 3.12.*
	
	# Build and push the image to the container registry
  vastde functions build my-registry/my-function --image-tag v1.0.0 --push
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--clear-cache` | bool | Clear build cache (automatically done when version changes) |  |
| `-H`, `--handlers` | string | Handler file name | `main.py` |
| `-T`, `--image-tag` | string | Image tag to apply | `latest` |
| `-P`, `--pull-policy` | string | Builder image pull policy (never|always|ifnotpresent) | `ifnotpresent` |
| `--push` | bool | Push the built image to the container registry |  |
| `-t`, `--target` | string | Function target folder (default is current directory) |  |
| `-V`, `--version` | string | Language version (e.g., Python: 3.12.*, 3.11.*; Go: 1.21) | `3.12.*` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

