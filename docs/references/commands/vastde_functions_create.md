---
title: vastde functions create
description: Create a VAST DataEngine function
---

# vastde functions create

Create a VAST DataEngine function

## Synopsis

Create a new function in VAST DataEngine from a container image.

This command registers a function with DataEngine, making it available for invocation by triggers
and pipelines. Creating a function requires:

1. Function name (--name): Unique identifier for the function
2. Container registry (--container-registry): Registry containing the function image
3. Artifact source (--artifact-source): Image name in the registry
4. Image tag (--image-tag): Specific version of the image to use

The function image must be built and pushed to the container registry before creating the function.
Use 'functions build' to create the image locally, then push it to your registry.

Optional configuration:
- --description: Human-readable description
- --tags: Custom labels for organization
- --architecture: Target architecture (e.g., amd64, arm64)
- --publish: Immediately publish the function for use
- --revision-alias: Friendly name for this revision
- --revision-description: Description of this revision

Functions can also be configured from a YAML file using --from-file, which supports all the
same options as command-line flags. Command-line flags take precedence over file values.

After creation, the function can be:
- Invoked directly using 'functions invoke'
- Triggered by events using 'triggers create'
- Integrated into pipelines using 'pipelines create'

```
vastde functions create [flags]
```

## Examples

```bash
  # Create a function with minimal required flags
  vastde functions create --name image-processor \
    --container-registry my-ecr-registry \
    --artifact-source vastdata/image-processor \
    --image-tag v1.0.0

  # Create function with description and tags for organization
  vastde functions create --name data-transformer \
    --container-registry my-ecr-registry \
    --artifact-source vastdata/transformer \
    --image-tag v2.1.0 \
    --description "Transforms JSON data to Parquet format" \
    --tags "production,etl,data-processing"

  # Create and immediately publish the function
  vastde functions create --name event-handler \
    --container-registry my-ecr-registry \
    --artifact-source vastdata/events \
    --image-tag latest \
    --publish

  # Create function with revision metadata
  vastde functions create --name ml-inference \
    --container-registry my-ecr-registry \
    --artifact-source vastdata/ml-model \
    --image-tag v1.5.2 \
    --revision-alias "stable" \
    --revision-description "Stable release with bug fixes"

  # Create function from YAML configuration file
  vastde functions create --from-file function-config.yaml

  # Create function with JSON output for automation scripts
  vastde functions create --name api-gateway \
    --container-registry my-ecr-registry \
    --artifact-source vastdata/gateway \
    --image-tag v3.0.0 \
    --output json

  # Dry-run to preview the API request without creating
  vastde functions create --name test-function \
    --container-registry my-ecr-registry \
    --artifact-source vastdata/test \
    --image-tag dev \
    --dry-run
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--architecture` | string | Architecture |  |
| `--artifact-source` | string | Artifact source (URL) |  |
| `--artifact-type` | string | Artifact type (supported: image) |  |
| `--container-registry` | string | Container registry name or VRN |  |
| `--default-revision-number` | int32 | Default revision number | `0` |
| `--description` | string | A description of the resource. (optional) |  |
| `-f`, `--from-file` | string | Path to function config file (yaml|json) |  |
| `--image-tag` | string | Image tag |  |
| `-n`, `--name` | string | A name for the resource |  |
| `--publish` | bool | Publish the function |  |
| `--revision-alias` | string | Revision alias |  |
| `--revision-description` | string | Revision description |  |
| `--tags` | stringSlice | Custom tags to apply. (optional) |  |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde functions](vastde_functions.md) - Manage VAST DataEngine functions

