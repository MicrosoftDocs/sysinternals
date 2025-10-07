--- 
TOCTitle: jcd
title: jcd
description: Enhanced directory navigation with substring matching for Linux and macOS.
ms:assetid: '6aaba8f7-8861-45fc-9e4d-18322da4271e'
ms.date: 10/07/2025
---

# jcd 1.0.1

**By Mark Russinovich**

Published: October 7, 2025

[**Download jcd for Linux and macOS (GitHub)**](https://github.com/microsoft/jcd)

## Introduction

`jcd` (jump change directory) is a Rust-based command-line tool that provides
enhanced directory navigation with substring matching and smart selection.
It's like the `cd` command, but with superpowers!

## Features

- Tab Navigation: Intelligent cycling through all matches with visual feedback and animated loading indicators
- Bidirectional Tab Cycling: Tab cycles forward, Shift+Tab cycles backward through matches
- Case Sensitivity Control: Use `-i` flag for case-insensitive matching (default is case-sensitive)
- Directory Ignore Support: Skip unwanted directories using `.jcdignore` files with regex patterns
- Flexible Ignore Configuration: Support for project-local, user, and system-wide ignore files
- First-Match Jump: Press Enter after typing to immediately navigate to the best match
- Priority Matching Order:
    1. Exact matches prioritized over partial matches
    2. Up-tree matches (parent directories) have highest priority
    3. Down-tree matches (subdirectories) sorted by proximity
    4. Alphabetical sorting within same priority level
- Substring Matching: Find directories by partial name matches
- Bidirectional Search: Searches both up the directory tree and down into subdirectories

## Usage

```text
Usage:
  jcd [-i] [-x] <directory_pattern>   - Changes directory according to the pattern

Flags:
  -i                     - Case-insensitive matching (default: case-sensitive)
  -x                     - Bypass ignore patterns (search all directories)

directory_pattern:
  jcd <substring>        # Navigate to directory matching substring
  jcd <absolute_path>    # Navigate to absolute path
  jcd <path/pattern>     # Navigate using path-like patterns
```

[**Download jcd for Linux and macOS (GitHub)**](https://github.com/microsoft/jcd)

**Runs on:**

- Linux
- macOS
