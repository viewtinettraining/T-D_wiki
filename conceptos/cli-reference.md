---
tags: [conceptos, cli, administracion, comandos, sistema]
tipo: tecnica
fuentes: ["viewtinet-cli-guide_en_v6.3.5_v1.0"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# CLI Reference

The Viewtinet CLI provides system administrators with direct command-line access to manage the platform's containerized services, run operational scripts, inspect logs, perform backups, and diagnose issues. The CLI complements the [[gui-overview|Viewtinet GUI]] and is the primary interface for advanced administration and troubleshooting.

## Access

The CLI is accessed via SSH to the Viewtinet server (standalone) or to either node in a [[ha-architecture|cluster deployment]]:

```bash
ssh viewtinet@<server-ip>
```

The `viewtinet` user is the operating system account created during [[os-setup|OS setup]]. All platform operations use `sudo` or dedicated scripts — direct root login is not recommended.

## Directory Structure

All Viewtinet platform files reside under `/opt/vn/`:

| Path | Contents |
|------|----------|
| `/opt/vn/config/` | Module configuration files |
| `/opt/vn/viewtinet-builder/scripts/` | Operational and maintenance scripts |
| `/opt/vn/dhyana/` | ETL pipeline definitions (XML-based) for [[etl-pipeline|VS Data Broker]] |
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
| `troubleshooting.sh` | Comprehensive health diagnostic — covers containers, [[ha-architecture|HA state]], disk, and services |
| `get_logs.sh` | Collect logs from all containers for support tickets |
| `check_ip.sh` | Verify IP binding on network interfaces |
| `check_vrrp.sh` | Show current VRRP state and [[ha-architecture|VIP]] ownership |

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
- **ETL debugging** — inspect [[vs-data-broker-overview|Dhyana]] XML definitions in `/opt/vn/dhyana/`
- **Platform updates** — updates are applied from [[viewtimanager-overview|ViewtiManager]] GUI (Admin → Updates) but can also be triggered via CLI

## Scope

The CLI guide applies to all [[viewtinet-platform-overview|Viewtinet product lines]] running on [[ubuntu-compatibility|Ubuntu Server 20.04 and 24.04]]: ViewtiLog, ViewtiMon, and ViewtiQoS. It is intended for system administrators, network engineers, and Viewtinet support personnel.

## Related Pages

- [[viewtimanager-overview]] — GUI-based administration
- [[ha-architecture]] — HA cluster management via CLI scripts
- [[vs-data-broker-overview]] — Dhyana ETL module accessed via CLI
- [[standalone-vs-cluster]] — deployment modes and their CLI implications
