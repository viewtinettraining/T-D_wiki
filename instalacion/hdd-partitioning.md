---
tags: [instalacion, hardware, almacenamiento]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# HDD Partitioning

Viewtinet strongly recommends separating the operating system disk group from the data warehouse disk group for optimal performance and redundancy. This scheme must be applied during [[os-setup|Ubuntu Server installation]] before starting the [[installation-bundle]].

## Disk Group Architecture

| Group | Purpose | RAID Type | Min Disks |
|---|---|---|---|
| Disk Group 1 | Operating System | RAID 1 | 2 |
| Disk Group 2 | Data Warehouse | RAID 10 (preferred) or RAID 5 | 2+ |

For servers with physical RAID controllers, configure RAID arrays directly on the controller. For NVMe servers without a physical controller, use Linux software RAID (`mdadm`).

## OS Partitions (Disk Group 1 — RAID 1, XFS)

| Mount Point | Size | Type | Filesystem |
|---|---|---|---|
| `/boot` | 1 GB | Primary | XFS |
| `swap` | 96 GB (or RAM size) | Primary | swap |
| `/` | 35 GB | Logical | XFS |
| `/home` | 50 GB | Logical | XFS |
| `/tmp` | 10 GB | Logical | XFS |
| `/var` | 100 GB | Logical | XFS |

## Data Warehouse Partitions (Disk Group 2 — ext4)

| Mount Point | Size | Notes |
|---|---|---|
| `/opt/vn` | 200 GB | Base Viewtinet data directory |
| `/opt/vn/viewticore/` | 1.2 TB | Core analytics storage |
| `/opt/vn/dhyana/var/data/` | 400 GB | Increase if more space is available |
| `/opt/vn/probe/var/` | 600 GB | Required only if [[viewtimon-installation|ViewtiMon]] is deployed |

## Virtual Machine Recommendations

In virtualized environments, maintain logical separation using two separate virtual disks:
- One virtual disk dedicated to the OS partitions
- One or more virtual disks for the Data Warehouse

This mirrors the physical disk group design and ensures manageability.

## Applying the Layout

During Ubuntu Server installation, select **Custom storage layout** to manually define partitions. Apply the correct RAID type and filesystem per the tables above. Refer to [[system-configuration]] for post-partitioning steps, and [[ubuntu-compatibility]] for supported OS versions.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
