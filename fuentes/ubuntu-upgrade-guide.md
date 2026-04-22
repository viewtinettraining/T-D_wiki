---
title: "Ubuntu Upgrade Guide — Source Section Index"
description: "This page catalogs the source files processed for the Ubuntu upgrade wiki section, covering the two-stage upgrade from Ubuntu 20.04 LTS to 24.04 LTS."
keywords: "fuente, ubuntu, instalacion"
---

# Ubuntu Upgrade Guide — Source Section Index

This page catalogs the source files processed for the [Ubuntu upgrade](../instalacion/ubuntu-upgrade.md) wiki section, covering the two-stage upgrade from Ubuntu 20.04 LTS to 24.04 LTS.

## Source Files

- `upgrade-to-ubuntu-24-dot-04/intro.md` — Introduction: two-stage upgrade requirement, IPMI access prerequisite
- `upgrade-to-ubuntu-24-dot-04/upgrade-stage-1.md` — Stage 1: Ubuntu 20.04 → 22.04 upgrade procedure
- `upgrade-to-ubuntu-24-dot-04/upgrade-stage-2.md` — Stage 2: Ubuntu 22.04 → 24.04 upgrade procedure, network interface rename fix

## Key Information Extracted

**Stage 1 (20.04 → 22.04):**
- Backup requirement, firewall rules for upgrade repositories
- `screen` session usage to prevent SSH disconnection
- `sudo do-release-upgrade` with specific answers to prompts (no Docker auto-restart, no to non-superuser packet capture, N for timesyncd and sysctl configs)
- Verification: `cat /etc/issue` should show `Ubuntu 22.04.5 LTS`

**Stage 2 (22.04 → 24.04):**
- Same approach as Stage 1
- Network interface naming change (e.g., `enp67s0f0` → `enp67s0f0np0`)
- Netplan configuration fix via `/etc/netplan/00-installer-config.yaml`
- Python 3.8 and pip installation required (not in default Ubuntu 24.04)
- Verification: `cat /etc/issue` should show `Ubuntu 24.04 LTS`

## Related Pages

- [Ubuntu Upgrade](../instalacion/ubuntu-upgrade.md) — Procedural wiki page for the full upgrade
- [Os Setup](../instalacion/os-setup.md) — Original Ubuntu OS setup
- [Ubuntu Compatibility](../conceptos/ubuntu-compatibility.md) — Supported OS versions for Viewtinet
- [System Configuration](../instalacion/system-configuration.md) — Post-install configuration steps
- [Viewtinet Appliance](../productos/viewtinet-appliance.md) — Hardware context for the upgrade
