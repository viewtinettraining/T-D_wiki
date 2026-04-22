---
title: "CLI Guide PDF — Source Summary"
description: "This page summarizes the Viewtinet CLI Guide (v6.3.5, v1.0), a reference for system administrators who manage the Viewtinet platform via the command line. Th..."
keywords: "fuentes, cli, administracion"
---

# CLI Guide PDF — Source Summary

This page summarizes the Viewtinet CLI Guide (v6.3.5, v1.0), a reference for system administrators who manage the [Viewtinet platform](../productos/viewtinet-platform-overview.md) via the command line. The guide covers microservice architecture, container management, operational scripts, log inspection, and system updates.

## Scope and Audience

The guide targets system administrators, network engineers, and support personnel using CLI on Ubuntu Server 20.04 and 24.04. It applies to all [Viewtinet product lines](../productos/viewtinet-platform-overview.md): ViewtiLog, ViewtiMon, and Viewtify QoS. The platform runs as Docker containers orchestrated under a [microservices architecture](../conceptos/cli-reference.md).

## Key Technical Areas

### Software Architecture
Viewtinet installs under `/opt/vn/` with a defined [directory structure](../conceptos/cli-reference.md):
- `/opt/vn/config/` — module configuration files
- `/opt/vn/viewtinet-builder/scripts/` — operational and maintenance scripts
- `/opt/vn/dhyana/` — ETL pipeline definitions (XML-based)
- `/opt/vn/viewticore/` — core data engine components
- `/opt/vn/software/` — Docker images

### Container Management
The `dps` alias (equivalent to `sudo docker ps`) lists all running containers. Module management uses per-module scripts at `/opt/vn/viewtinet-builder/scripts/<module>/action-module.sh` accepting `start`, `stop`, or `restart` parameters. See [Cli Reference](../conceptos/cli-reference.md) for all commands.

### Operational Scripts
Located in `/opt/vn/viewtinet-builder/scripts/`:
- `start-all.sh` / `stop-all.sh` — full platform lifecycle
- `export-backup.sh` / `import-backup.sh` — MongoDB and config backups
- `troubleshooting.sh` — comprehensive health diagnostic tool
- `get_logs.sh`, `check_ip.sh`, `check_vrrp.sh` — diagnostics

## Related Pages

- [Cli Reference](../conceptos/cli-reference.md) — detailed CLI command reference
- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — ViewtiManager module
- [Ha Architecture](../conceptos/ha-architecture.md) — HA module checks via `troubleshooting.sh`
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — Dhyana ETL module
