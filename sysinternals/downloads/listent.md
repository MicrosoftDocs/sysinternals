--- 
TOCTitle: listent
title: listent
description: Command-line tool to discover and list code signing entitlements for macOS executable binaries.
ms:assetid: 'f0c27008-0bfa-4180-b7d0-9e2f098323aa'
ms.date: 03/26/2026
---

# listent 1.0

**By Mario Hewardt**

Published: March 26, 2026

[**Download listent for macOS (GitHub)**](https://github.com/microsoft/Sysinternals-listent)

## Introduction

A command-line tool to discover and list code signing entitlements for macOS executable binaries. Supports static scanning, real-time process monitoring, and background daemon operation.

`listent` recursively scans directories to find executable binaries and extracts their code signing entitlements. It's designed for security researchers, developers, and system administrators who need to audit or understand the permissions requested by macOS applications.

## Features

### Core Capabilities
- **Fast scanning**: Efficiently traverses directory trees with smart filtering and progress indicators
- **Entitlement extraction**: Uses macOS `codesign` to extract entitlements from binaries
- **Flexible filtering**: Filter by paths and specific entitlement keys with glob pattern support
- **Multiple output formats**: Human-readable and structured JSON output
- **Multiple paths**: Scan multiple directories in a single command
- **Graceful interrupts**: Clean cancellation with Ctrl+C

## Operating Modes

### 1. Static Scan Mode (Default)
Scan files and directories for entitlements:
```bash
# Scan default locations (/usr/bin and /usr/sbin)
listent

# Scan specific paths
listent /usr/bin /usr/sbin

# Filter by entitlement patterns
listent -e "com.apple.security.*"
listent -e "*network*" -e "*debug*"

# JSON output for automation
listent /usr/bin -e "*security*" --json
```

### 2. Real-time Monitor Mode
Monitor new processes for entitlements:
```bash
# Monitor all new processes
listent monitor

# Monitor with custom polling interval
listent monitor --interval 0.5

# Monitor specific entitlements only
listent monitor -e "com.apple.security.network.*"
```

### 3. Daemon Mode
Run monitoring continuously in the foreground (useful for testing or manual daemon operation):
```bash
# Run as daemon in foreground
listent daemon run

# Daemon with custom config file
listent daemon run --config /etc/listent/custom.toml
```

Custom configuration file template (`daemon.toml`):
```toml
[daemon]
# How often to poll for new processes, in seconds (0.1 - 300.0)
polling_interval = 1.0
# Start automatically when loaded by launchd (RunAtLoad)
auto_start = true

[monitoring]
# Filesystem paths to scan for running process binaries.
# Empty list = monitor processes from all paths.
path_filters = ["/usr/bin", "/usr/sbin"]
# Entitlement patterns to match (glob syntax). Empty list = all entitlements.
# Examples: "com.apple.security.*", "*network*"
entitlement_filters = []
```

Query logs with:
```bash
# View listent logs in real-time
log stream --predicate 'subsystem == "com.microsoft.sysinternals.listent"' --level info

# View recent logs
log show --predicate 'subsystem == "com.microsoft.sysinternals.listent"' --last 1h

# Filter for errors only
log show --predicate 'subsystem == "com.microsoft.sysinternals.listent" AND messageType == error' --last 24h
```

### 4. Background Daemon Service
Run monitoring as a persistent system service managed by launchd:
```bash
# Install and start daemon
sudo listent daemon install

# Check daemon status
listent daemon status

# View daemon logs
listent daemon logs
listent daemon logs --since 1h
listent daemon logs --since 30m
listent daemon logs --since "2025-01-15 10:00"
listent daemon logs --format json
listent daemon logs -f                    # Follow logs in real-time

# Stop daemon process
listent daemon stop

# Uninstall service
sudo listent daemon uninstall
```

## Examples

### Static Scanning
```bash
# Basic scan with progress (uses default /usr/bin and /usr/sbin)
listent

# Multi-directory scan with filtering
listent /usr/bin /usr/sbin -e "*security*"

# Find all network-related entitlements
listent -e "*network*" --json | jq '.results[].entitlements'

# Scan quietly (suppress warnings)
listent /usr/bin --quiet
```

### Process Monitoring
```bash
# Monitor all processes with 2-second intervals
listent monitor --interval 2.0

# Monitor only security-related entitlements
listent monitor -e "com.apple.security.*"

# Run as daemon with custom config
listent daemon run --config /etc/listent/daemon.toml
```

### Daemon Management
```bash
# Install daemon with default monitoring (requires sudo)
sudo listent daemon install

# Install with custom configuration file
sudo listent daemon install --config /path/to/config.toml

# View recent daemon activity
listent daemon logs --since 1h

# Check if daemon is running
listent daemon status

# Stop and remove daemon
listent daemon stop
sudo listent daemon uninstall
```

## Configuration

### Command Line Options
- **Paths**: Multiple paths can be specified as positional arguments: `listent /path1 /path2`
- **Entitlement filtering**: `-e "pattern"` supports exact matches and globs (`*`, `?`, `[]`)
- **Output format**: `--json` or `-j` for structured output, default is human-readable
- **Quiet mode**: `--quiet` or `-q` suppresses warnings about unreadable files
- **Monitoring**: `listent monitor` subcommand enables real-time process monitoring
- **Monitor interval**: `--interval SECONDS` sets polling frequency (0.1-300.0, default: 1.0)
- **Daemon mode**: `listent daemon run` runs as background daemon process
- **Daemon management**: `listent daemon install|uninstall|status|stop|logs`
- **Config file**: `--config FILE` or `-c FILE` specifies daemon configuration path

### Entitlement Patterns
```bash
# Exact match
-e "com.apple.security.network.client"

# Wildcard patterns
-e "com.apple.security.*"        # All Apple security entitlements
-e "*network*"                   # Any entitlement containing "network"
-e "*.debug.*"                   # Debug-related entitlements

# Multiple patterns (OR logic)
-e "com.apple.private.*" -e "*.debug.*"
```

### Daemon Configuration
Daemon settings are configured via a TOML configuration file:
- **Default location**: `~/.config/listent/daemon.toml`
- **Custom path**: Use `--config` with `daemon install`

To change configuration, edit the config file and restart the daemon:
```bash
# Edit config
nano ~/.config/listent/daemon.toml

# Restart daemon
listent daemon stop
sudo listent daemon install
```

Example daemon configuration:
```toml
[daemon]
polling_interval = 1.0
auto_start = true

[monitoring]
path_filters = []
entitlement_filters = ["com.apple.security.*", "*network*"]

[logging]
level = "info"
subsystem = "com.microsoft.sysinternals.listent"
category = "daemon"
```

## Troubleshooting

### Ctrl+C Not Working in External Terminals

If Ctrl+C doesn't interrupt the scan in Terminal.app or iTerm2, this is due to a macOS terminal signal handling issue.

**Workaround**: Before running `listent`, execute:
```bash
trap - INT
```

This removes any existing interrupt trap and restores the default SIGINT behavior. After this, Ctrl+C should work normally.

Note: This issue doesn't affect VS Code's integrated terminal.

## Output Formats

### Human-Readable (Default)
```
Found 2 binaries with 5 total entitlements:

/usr/bin/security:
  com.apple.private.platformsso.security: true

/usr/bin/nc:
  com.apple.security.network.client: true
  com.apple.security.network.server: true

Scan Summary:
  Scanned: 156 files
  Matched: 2 files
  Duration: 2.34s
```

### JSON Format
```json
{
  "results": [
    {
      "path": "/usr/bin/security",
      "entitlements": {
        "com.apple.private.platformsso.security": true
      },
      "entitlement_count": 1
    }
  ],
  "summary": {
    "scanned": 156,
    "matched": 2,
    "duration_ms": 2340,
    "skipped_unreadable": 0
  }
}
```

## Security

If you believe you have found a security issue, please report it via [the project's GitHub repository](https://github.com/microsoft/Sysinternals-listent/issues) rather than opening a public issue.

[**Download jcd for Linux and macOS (GitHub)**](https://github.com/microsoft/Sysinternals-listent)

**Runs on:**

- macOS
