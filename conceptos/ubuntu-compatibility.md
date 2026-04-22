---
tags: [conceptos, os, ubuntu, compatibilidad]
tipo: concepto
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
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
- Viewtinet's purpose-built [[viewtinet-appliance|hardware appliances]]
- Virtual machines
- COTS (Commercial Off-The-Shelf) servers

The documentation does **not** cover:
- Creating Ubuntu installation media
- Connecting to physical servers for OS installation
- Deploying Ubuntu on VMs or cloud environments
- The disk partitioning process itself (guidelines are provided in [[hdd-partitioning]])

All procedures in the installation guide begin **after** the OS is installed and partitioned.

## Required Skills

The installation documentation is intended for personnel experienced in:
- Linux-based server administration (Ubuntu Server specifically)
- Observability and monitoring practices
- Docker and containerized environments

Users must be proficient in command-line operations and system configuration tasks.

## Post-OS Requirements

After installing Ubuntu 20.04 or 24.04, the following must be configured before Viewtinet installation:

1. [[os-setup]] — Create the mandatory `viewtinet` user
2. [[hdd-partitioning]] — Apply the recommended partition scheme
3. [[system-configuration]] — Configure SSH (OpenSSH Server) and NTP synchronization

For upgrade paths between versions, see [[ubuntu-upgrade]].

See [[installation-guide-hub|Installation Guide Hub]] for the full installation source index.
