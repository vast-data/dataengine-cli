---
title: vastde completion
description: Generate the autocompletion script for the specified shell
---

# vastde completion

Generate the autocompletion script for the specified shell

## Synopsis

Generate the autocompletion script for vastde for the specified shell.
See each sub-command's help for details on how to use the generated script.

```
vastde completion [bash|zsh|fish|powershell]
```

## Options

### Global options

| Flag | Type | Description | Default |
|------|------|-------------|----------|
| `--dry-run` | bool | Simulate the operation without making actual changes to the system |  |
| `-o`, `--output` | string | Output format: json|yaml|human | `human` |
| `-v`, `--verbose` | int | Verbosity level (0-9): 0=standard, 1=verbose, 2=detailed, 3=extended, 4=debug, 5=trace | `0` |

## See Also

- [vastde](vastde.md) - VAST DataEngine CLI

