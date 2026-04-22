---
title: "CLI Reference"
description: "The Viewtinet CLI provides system administrators with direct command-line access to manage the platform's containerized services, run operational scripts, in..."
keywords: "conceptos, cli, administracion, comandos, sistema"
---

# CLI Reference

The Viewtinet CLI provides system administrators with direct command-line access to manage the platform's containerized services, run operational scripts, inspect logs, perform backups, and diagnose issues. The CLI complements the [Viewtinet GUI](../configuracion/gui-overview.md) and is the primary interface for advanced administration and troubleshooting.

## Access

The CLI is accessed via SSH to the Viewtinet server (standalone) or to either node in a [cluster deployment](ha-architecture.md):

```bash
ssh viewtinet@<server-ip>
```

The `viewtinet` user is the operating system account created during [OS setup](../instalacion/os-setup.md). All platform operations use `sudo` or dedicated scripts — direct root login is not recommended.

## Directory Structure

All Viewtinet platform files reside under `/opt/vn/`:

| Path | Contents |
|------|----------|
| `/opt/vn/config/` | Module configuration files |
| `/opt/vn/viewtinet-builder/scripts/` | Operational and maintenance scripts |
| `/opt/vn/dhyana/` | ETL pipeline definitions (XML-based) for [VS Data Broker](etl-pipeline.md) |
| `/opt/vn/viewticore/` | Core data engine components |
| `/opt/vn/software/` | Docker images |

## Container Management

The platform runs as Docker containers. The `dps` alias (equivalent to `sudo docker ps`) lists all running containers and their status. This is the first command to run when diagnosing issues.

Per-module control is done via scripts at:
```
/opt/vn/viewtinet-builder/scripts/<module>/action-module.sh
```

Usage: `./action-module.sh start | stop | restart`

## Operational Scripts

All scripts are located in `/opt/vn/viewtinet-builder/scripts/`:

| Script | Description |
|--------|-------------|
| `start-all.sh` | Start all platform services |
| `stop-all.sh` | Stop all platform services |
| `export-backup.sh` | Export MongoDB data and configuration backups |
| `import-backup.sh` | Restore from a backup archive |
| `troubleshooting.sh` | Comprehensive health diagnostic — covers containers, [HA state](ha-architecture.md), disk, and services |
| `get_logs.sh` | Collect logs from all containers for support tickets |
| `check_ip.sh` | Verify IP binding on network interfaces |
| `check_vrrp.sh` | Show current VRRP state and [VIP](ha-architecture.md) ownership |

## Log Inspection

Container logs are accessible via:
```bash
sudo docker logs <container-name> --tail 100 -f
```

The `get_logs.sh` script collects and bundles logs from all containers into a single archive for submission to Viewtinet support.

## Key Use Cases

- **Service restart** — restart a specific module after configuration change
- **HA health check** — run `check_vrrp.sh` and `troubleshooting.sh` to verify cluster state
- **Backup and restore** — use `export-backup.sh` / `import-backup.sh` for disaster recovery
- **ETL debugging** — inspect [Dhyana](../productos/vs-data-broker-overview.md) XML definitions in `/opt/vn/dhyana/`
- **Platform updates** — updates are applied from [ViewtiManager](../productos/viewtimanager-overview.md) GUI (Admin → Updates) but can also be triggered via CLI

## Scope

The CLI guide applies to all [Viewtinet product lines](../productos/viewtinet-platform-overview.md) running on [Ubuntu Server 20.04 and 24.04](ubuntu-compatibility.md): ViewtiLog, ViewtiMon, and ViewtiQoS. It is intended for system administrators, network engineers, and Viewtinet support personnel.

## Related Pages

- [Viewtimanager Overview](../productos/viewtimanager-overview.md) — GUI-based administration
- [Ha Architecture](ha-architecture.md) — HA cluster management via CLI scripts
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — Dhyana ETL module accessed via CLI
- [Standalone Vs Cluster](standalone-vs-cluster.md) — deployment modes and their CLI implications
