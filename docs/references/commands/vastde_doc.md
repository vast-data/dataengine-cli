---
title: vastde doc
description: Generate CLI documentation
---

# vastde doc

Generate CLI documentation

## Synopsis

Generate markdown documentation for all CLI commands.

This command generates LLM-friendly documentation for the VAST DataEngine CLI.
The documentation is organized in a hierarchical structure under docs/references/commands/.

```
vastde doc [flags]
```

## Examples

```bash
  # Generate documentation in the default location (./docs)
  vastde doc

  # Generate documentation in a custom location
  vastde doc --output-dir /path/to/docs
```

## Options

### Command-specific options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--output-dir` | string | Output directory for generated documentation | `./docs` |

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

