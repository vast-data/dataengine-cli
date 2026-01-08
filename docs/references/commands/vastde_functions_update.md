---
title: vastde functions update
description: Update a VAST DataEngine function
---

# vastde functions update

Update a VAST DataEngine function

## Synopsis

Update configuration of an existing function.

This command modifies properties of a function identified by its GUID or name. You can update:

- Description (--description)
- Tags (--tags)
- Container image and registry (--artifact-source, --container-registry, --image-tag)
- Architecture (--architecture)
- Published status (--publish)
- Revision configuration (--revision-alias, --revision-description, --default-revision-number)
- Custom configuration (via YAML file)

Updates can be specified via command-line flags or a YAML configuration file (--from-file).
When using a file, command-line flags take precedence over file values.

Important notes:
- Function name cannot be changed after creation
- Updates create a new revision of the function
- The update operation uses a GET-modify-PUT pattern to preserve existing settings
- Only explicitly specified properties are modified

The update workflow:
1. Fetches current function configuration
2. Fetches latest revision details
3. Applies your specified changes
4. Creates a new revision with the updates
5. Optionally publishes the new revision

Use --publish to immediately make the updated function available for use. Without this flag,
the update creates a new revision but doesn't make it the default.

Common update scenarios:
- Deploy new image version: --image-tag v2.0 --publish
- Change description: --description "Updated description"
- Add tags: --tags environment:production,version:v2

```
vastde functions update [guid|name] [flags]
```

## Examples

```bash
  # Update function description
  vastde functions update image-processor \
    --description "Enhanced image processing with ML capabilities"

  # Update function to use a new image tag
  vastde functions update image-processor \
    --image-tag v2.0.0

  # Update image tag and publish the new revision
  vastde functions update image-processor \
    --image-tag v2.1.0 \
    --publish

  # Update multiple properties at once
  vastde functions update data-transformer \
    --description "Production-ready data transformer" \
    --tags "production,etl,critical" \
    --image-tag v3.0.0 \
    --publish

  # Update using function GUID instead of name
  vastde functions update a1b2c3d4-e5f6-7890-abcd-ef1234567890 \
    --image-tag v1.5.1 \
    --publish

  # Update with revision metadata
  vastde functions update ml-inference \
    --image-tag v2.0.0 \
    --revision-alias "stable-v2" \
    --revision-description "Major version upgrade with new features"

  # Update from YAML configuration file
  vastde functions update event-handler --from-file updated-config.yaml

  # Dry-run to preview changes without applying
  vastde functions update api-gateway \
    --image-tag v4.0.0 \
    --dry-run

  # Update and output result as JSON for automation
  vastde functions update processor \
    --image-tag v1.2.3 \
    --publish \
    --output json
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

