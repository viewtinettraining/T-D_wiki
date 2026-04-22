---
tags: [fuentes, cli, administracion]
tipo: fuente
fuentes: ["viewtinet-cli-guide_en_v6.3.5"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# CLI Guide PDF — Source Summary

This page summarizes the Viewtinet CLI Guide (v6.3.5, v1.0), a reference for system administrators who manage the [[viewtinet-platform-overview|Viewtinet platform]] via the command line. The guide covers microservice architecture, container management, operational scripts, log inspection, and system updates.

## Scope and Audience

The guide targets system administrators, network engineers, and support personnel using CLI on Ubuntu Server 20.04 and 24.04. It applies to all [[viewtinet-platform-overview|Viewtinet product lines]]: ViewtiLog, ViewtiMon, and Viewtify QoS. The platform runs as Docker containers orchestrated under a [[cli-reference|microservices architecture]].

## Key Technical Areas

### Software Architecture
Viewtinet installs under `/opt/vn/` with a defined [[cli-reference|directory structure]]:
- `/opt/vn/config/` — module configuration files
- `/opt/vn/viewtinet-builder/scripts/` — operational and maintenance scripts
- `/opt/vn/dhyana/` — ETL pipeline definitions (XML-based)
- `/opt/vn/viewticore/` — core data engine components
- `/opt/vn/software/` — Docker images

### Container Management
The `dps` alias (equivalent to `sudo docker ps`) lists all running containers. Module management uses per-module scripts at `/opt/vn/viewtinet-builder/scripts/<module>/action-module.sh` accepting `start`, `stop`, or `restart` parameters. See [[cli-reference]] for all commands.

### Operational Scripts
Located in `/opt/vn/viewtinet-builder/scripts/`:
- `start-all.sh` / `stop-all.sh` — full platform lifecycle
- `export-backup.sh` / `import-backup.sh` — MongoDB and config backups
- `troubleshooting.sh` — comprehensive health diagnostic tool
- `get_logs.sh`, `check_ip.sh`, `check_vrrp.sh` — diagnostics

## Related Pages

- [[cli-reference]] — detailed CLI command reference
- [[viewtimanager-overview]] — ViewtiManager module
- [[ha-architecture]] — HA module checks via `troubleshooting.sh`
- [[vs-data-broker-overview]] — Dhyana ETL module
