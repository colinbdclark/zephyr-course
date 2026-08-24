# Iomico Zephyr Course Training Environment

This repository includes Iomico's ready-to-use
development environment based on Zephyr 4.4.2 for their Zephyr training course, modified by Colin Clark to use nix and direnv.

## Requirements

- [Nix](https://nixos.org/download) with flakes enabled
- [direnv](https://direnv.net)

## Setup Zephyr with Nix

### 1. Clone the repository

The repository must live inside a parent directory that will become the Zephyr workspace:

```console
mkdir -p zephyr-course-workspace
cd zephyr-course-workspace
git clone https://github.com/colinbdclark/zephyr-course.git
cd zephyr-course
```

### 2. Activate the Devshell

To start the nix devshell, run `nix develop` in the repository's directory. Or use `direnv allow` to automatically start the dev shell whenever you enter the repository's directory.

### 3. Initialize the Zephyr Workspace

```console
west init -l .
west update
direnv reload
```

### 4. Build the app:

```console
west build -p always -b <your_board> app
```
