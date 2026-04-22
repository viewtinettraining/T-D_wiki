---
title: "Ubuntu Compatibility"
description: "Viewtinet is compatible only with Ubuntu Server in two specific LTS versions. Installation on any other operating system version or Linux distribution is not..."
keywords: "conceptos, os, ubuntu, compatibilidad"
---

# Ubuntu Compatibility

Viewtinet is compatible **only** with Ubuntu Server in two specific LTS versions. Installation on any other operating system version or Linux distribution is not supported.

## Supported Versions

| Operating System | Version | Status |
|---|---|---|
| Ubuntu Server | 20.04 LTS | Fully Supported |
| Ubuntu Server | 24.04 LTS | Fully Supported |
| Other Linux distributions | Any | Not Supported |
| Windows, macOS | Any | Not Supported |

## Scope of Support

The Ubuntu compatibility requirement applies to all Viewtinet deployment scenarios:
- Viewtinet's purpose-built [hardware appliances](../productos/viewtinet-appliance.md)
- Virtual machines
- COTS (Commercial Off-The-Shelf) servers

The documentation does **not** cover:
- Creating Ubuntu installation media
- Connecting to physical servers for OS installation
- Deploying Ubuntu on VMs or cloud environments
- The disk partitioning process itself (guidelines are provided in [Hdd Partitioning](../instalacion/hdd-partitioning.md))

All procedures in the installation guide begin **after** the OS is installed and partitioned.

## Required Skills

The installation documentation is intended for personnel experienced in:
- Linux-based server administration (Ubuntu Server specifically)
- Observability and monitoring practices
- Docker and containerized environments

Users must be proficient in command-line operations and system configuration tasks.

## Post-OS Requirements

After installing Ubuntu 20.04 or 24.04, the following must be configured before Viewtinet installation:

1. [Os Setup](../instalacion/os-setup.md) — Create the mandatory `viewtinet` user
2. [Hdd Partitioning](../instalacion/hdd-partitioning.md) — Apply the recommended partition scheme
3. [System Configuration](../instalacion/system-configuration.md) — Configure SSH (OpenSSH Server) and NTP synchronization

For upgrade paths between versions, see [Ubuntu Upgrade](../instalacion/ubuntu-upgrade.md).

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full installation source index.
