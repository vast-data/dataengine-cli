---
title: vastde functions init
description: Generate a VAST DataEngine function scaffold
---

# vastde functions init

Generate a VAST DataEngine function scaffold

## Synopsis

Initialize a new VAST DataEngine function project with scaffolding and templates.

This command generates a basic function project structure with the specified function name.
The function name is used to create a project directory containing:
- Function handler template code
- Configuration files (requirements.txt, Aptfile, customDeps)
- Dependencies manifest
- Sample code demonstrating function patterns
- README.md with comprehensive development guide

The scaffolding provides a starting point for function development with best practices built in.
Currently supported language templates:
- python-pip: Python function with pip package management

After initialization, you can:
1. Navigate to the function directory (created with the function name)
2. Modify the handler code to implement your business logic
3. Add dependencies to the requirements file
4. Build the function image using 'functions build'
5. Deploy the function to DataEngine using 'functions create'

The --target flag specifies where to create the project directory (defaults to current directory).
The --handlers flag specifies the name of the main handler file (defaults to main.py).

## Examples

```bash
  # Initialize Python function scaffold in current directory
  vastde functions init python-pip my-function

  # Initialize function scaffold in specific directory
  vastde functions init python-pip event-processor --target ./my-functions

  # Initialize with custom handler file name
  vastde functions init python-pip data-processor \
    --target ./my-functions \
    --handlers custom_handler.py

  # Complete workflow: init, build, and deploy
  vastde functions init python-pip image-processor --target ./my-functions
  cd ./my-functions/image-processor
  # Edit handler code...
  vastde functions build image-processor --target ./my-functions/image-processor
  vastde functions create --name image-processor --image-tag latest ...
```

## Subcommands

- [python-pip](vastde_functions_init_python-pip.md) - Generate a Python pip scaffold for a vast function

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-H`, `--handlers` | string | Name of the handlers file (default is main.py) | `main.py` |
| `-t`, `--target` | string | The function target folder (default is current directory) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

