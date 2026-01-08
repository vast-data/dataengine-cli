---
title: vastde functions localrun
description: Run a built VAST DataEngine function as a local container
---

# vastde functions localrun

Run a built VAST DataEngine function as a local container

## Synopsis

Run a built function container locally using Docker for testing and development.

This command starts a function container on your local machine, allowing you to test function
behavior before deploying to DataEngine. The function runs in Docker and exposes an HTTP endpoint
for receiving CloudEvents.

Prerequisites:
- Docker must be installed and running
- Function image must be built using 'functions build'

Runtime configuration:
- --port: Local port to expose (default: 8080)
- --config: Path to config.yaml with environment variables and secrets
- --loglevel: Function log level (DEBUG|INFO|WARNING|ERROR|CRITICAL)
- --image-tag: Image tag to run (default: latest)
- --detach: Run in background mode

The config.yaml file can define:
- envs: Environment variables passed to the function
- secrets: Secret data mounted as files in /secrets directory

After starting the function, use 'functions invoke' to send test events:
  vastde functions invoke --generate-event --url http://localhost:8080/

In foreground mode, logs appear in real-time. Press Ctrl+C to stop the function.
In detached mode (--detach), the container runs in the background.

Local testing workflow:
1. Build function: vastde functions build my-function
2. Run locally: vastde functions localrun my-function
3. Test: vastde functions invoke --generate-event
4. Iterate on code and rebuild as needed

```
vastde functions localrun [name] [flags]
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `-c`, `--config` | string | Path to config.yaml file |  |
| `-d`, `--detach` | bool | Run the container in detached mode |  |
| `-T`, `--image-tag` | string | Image tag to run | `latest` |
| `-l`, `--loglevel` | string | Function log level (defaults to INFO) | `INFO` |
| `-p`, `--port` | int | Local port to bind to the function container | `8080` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

