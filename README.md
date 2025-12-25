# VAST DataEngine CLI

Version: v5.5.0-dev.789a7a64

> Command-line interface for managing and building applications on the VAST DataEngine platform.

## Welcome

Welcome to the VAST DataEngine CLI! This is your doorway to building and managing VAST DataEngine functions, pipelines, triggers, and compute resources.

## Features

- **Comprehensive Resource Management**: Manage functions, pipelines, triggers, compute clusters, container registries, buckets, and topics
- **Multiple Output Formats**: Support for human-readable, JSON, and YAML output formats
- **Configuration Management**: Built-in config commands for managing CLI settings and credentials
- **Dry-Run Mode**: Test operations safely without making actual changes
- **Verbose Logging**: Detailed logging with configurable verbosity levels (0-9)
- **Integrated Monitoring**: Built-in access to logs and traces for debugging
- **Auto-generated Documentation**: Self-documenting with `vastde doc` command

## Installation

Download the `vastde` binary for your platform from the [releases page][releases], or use the instructions below.

### macOS (Apple Silicon)

```bash
curl -fsSL -o vastde https://github.com/vast-data/dataengine-cli/releases/download/v5.5.0-dev.789a7a64/vastde_darwin_arm64
chmod +x vastde
sudo mv vastde /usr/local/bin
```

### macOS (Intel)

```bash
curl -fsSL -o vastde https://github.com/vast-data/dataengine-cli/releases/download/v5.5.0-dev.789a7a64/vastde_darwin_amd64
chmod +x vastde
sudo mv vastde /usr/local/bin
```

### Linux (x86_64)

```bash
curl -fsSL -o vastde https://github.com/vast-data/dataengine-cli/releases/download/v5.5.0-dev.789a7a64/vastde_linux_amd64
chmod +x vastde
sudo mv vastde /usr/local/bin
```

### Linux (ARM64)

```bash
curl -fsSL -o vastde https://github.com/vast-data/dataengine-cli/releases/download/v5.5.0-dev.789a7a64/vastde_linux_arm64
chmod +x vastde
sudo mv vastde /usr/local/bin
```

### Windows (x86_64)

Download [vastde_windows_amd64.exe](https://github.com/vast-data/dataengine-cli/releases/download/v5.5.0-dev.789a7a64/vastde_windows_amd64.exe) and add it to your PATH.

### Verify Installation

```bash
vastde version
```

## Quick Start

After installing the CLI, configure it to connect to your VAST Management Service (VMS):

```bash
# Initialize configuration
vastde config init

# Set your cluster endpoint
vastde config set --vms-url https://your-vast-cluster.com

# Set your authentication credentials
vastde config set --username <username> --password <password> --tenant <tenant>

# Verify configuration
vastde config view

# List available functions
vastde functions list

# Get help for any command
vastde functions --help
```

## Usage

### Available Commands

- **`buckets`** - Manage VAST DataEngine buckets
- **`builders`** - View and select VAST DataEngine builder images
- **`compute-clusters`** - Manage VAST DataEngine compute clusters
- **`config`** - Manage CLI configuration
- **`container-registries`** - Manage VAST DataEngine container registries
- **`doc`** - Generate CLI documentation
- **`functions`** - Manage VAST DataEngine functions
- **`logs`** - View VAST DataEngine logs
- **`metrics`** - View VAST DataEngine metrics
- **`pipelines`** - Manage VAST DataEngine pipelines
- **`setup-dataengine`** - Setup VAST DataEngine provisioning
- **`topics`** - Manage VAST DataEngine topics
- **`traces`** - View VAST DataEngine traces
- **`triggers`** - Manage VAST DataEngine triggers
- **`version`** - CLI version

### Command Reference

Visit our [CLI Reference Documentation][commands] to learn about each command in detail.

You can also explore each command through the terminal:

```bash
vastde --help
vastde [command] --help
vastde help [command]
```

### Global Flags

All commands support these global flags:

| Flag | Description |
|------|-------------|
| `-o, --output` | Output format: `json`, `yaml`, or `human` (default) |
| `-v, --verbose` | Verbosity level from 0-9 (0=standard, 9=trace) |
| `--dry-run` | Simulate operations without making changes |
| `--tenant` | Target tenant for multi-tenant clusters |

## Configuration

The CLI stores configuration in `~/.vastde/config.yaml`:

```yaml
endpoint: https://your-vast-cluster.example.com
token: <your-authentication-token>
tenant: default
output: human
```

## Shell Completion

Enable shell completion for enhanced productivity:

```bash
# Bash
vastde completion bash > /etc/bash_completion.d/vastde

# Zsh
vastde completion zsh > "${fpath[1]}/_vastde"

# Fish
vastde completion fish > ~/.config/fish/completions/vastde.fish
```

## Documentation

For complete documentation, visit the [VAST DataEngine Documentation](https://support.vastdata.com/s/topic/0TO5e000000cN2AGAU/vast-dataengine).

Generate local documentation:

```bash
vastde doc --output-dir ./docs
```

## Support

- **Issues**: [GitHub Issues](https://github.com/vast-data/dataengine-cli/issues)
- **Email**: support@vastdata.com

## License

Copyright VAST Data Ltd. All rights reserved.

[commands]: docs/references/commands/vastde.md
[releases]: https://github.com/vast-data/dataengine-cli/releases
