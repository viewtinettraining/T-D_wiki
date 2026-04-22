---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Standalone vs Cluster Deployment'
id: KNK-Y76-M84-ZE3
slug: standalone-vs-cluster
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Standalone vs Cluster Deployment

Viewtinet supports two primary deployment modes for its modules: standalone (single-node) and cluster (High Availability). Choosing the right mode depends on your availability requirements, hardware budget, and module type.

## Standalone Mode

In standalone mode, all services run on a single server. ViewtiSight, ViewtiManager, ViewtiAuth, and Viewticore are all installed together as part of the [standard bundle installation](../instalacion/installation-bundle-steps.md).

**When to use:**
- Development, test, or proof-of-concept environments
- Smaller deployments where downtime is acceptable
- [ViewtiMon](../productos/viewtimon-overview.md) (HA not supported — standalone only)
- [ViewtiQoS](../productos/viewtiqos-overview.md) (HA not supported — standalone only)

**Limitations:**
- Single point of failure
- No automatic failover
- Maintenance requires planned downtime

## Cluster (HA) Mode

In cluster mode, two or more nodes operate together with automatic failover. A floating Virtual IP (VIP) is managed by Keepalived, and HAProxy provides load balancing.

**When to use:**
- Production environments requiring continuous availability
- [ViewtiLog](../productos/viewtilog-overview.md) with high ingest volumes
- [ViewtiSight](../productos/viewtisight-overview.md) for uninterrupted analytics access

### Cluster Architecture

| Component | Role |
|---|---|
| Keepalived | Manages the floating VIP; promotes backup node on primary failure |
| HAProxy | Load balances incoming connections across nodes |
| Node 1 (master) | Handles traffic by default |
| Node 2 (mirror) | Takes over automatically if Node 1 fails |
| Dedicated inter-node NIC | Carries heartbeat, state sync, and replication traffic |

### Cluster Requirements

- At least 2 nodes with homogeneous hardware (identical CPU, RAM, storage recommended)
- A dedicated floating VIP (IPv4)
- NTP synchronization on all nodes — see [System Configuration](../instalacion/system-configuration.md)
- Each node requires its own license — see [Server Info](../instalacion/server-info.md) and [Upload License](../instalacion/upload-license.md)
- Dedicated inter-node network interface for heartbeat (recommended)

## Module HA Support Matrix

| Module | Standalone | Cluster/HA |
|---|---|---|
| ViewtiSight | Yes (default) | Yes — [Viewtisight Installation](../instalacion/viewtisight-installation.md) |
| ViewtiLog | Yes | Yes — [Viewtilog Installation](../instalacion/viewtilog-installation.md) |
| ViewtiMon | Yes | No — standalone only |
| ViewtiQoS | Yes | No — standalone only |

See [Ha Architecture](ha-architecture.md) for the broader HA architecture overview, and [Installation Guide Hub](../fuentes/installation-guide-hub.md) for source documentation.
