---
tags: [fuente, ubuntu, instalacion]
tipo: fuente
fuentes: ["snazzydocs-ubuntu-upgrade"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Ubuntu Upgrade Guide — Source Section Index

This page catalogs the source files processed for the [[ubuntu-upgrade|Ubuntu upgrade]] wiki section, covering the two-stage upgrade from Ubuntu 20.04 LTS to 24.04 LTS.

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

- [[ubuntu-upgrade]] — Procedural wiki page for the full upgrade
- [[os-setup]] — Original Ubuntu OS setup
- [[ubuntu-compatibility]] — Supported OS versions for Viewtinet
- [[system-configuration]] — Post-install configuration steps
- [[viewtinet-appliance]] — Hardware context for the upgrade
