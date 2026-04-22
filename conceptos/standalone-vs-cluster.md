---
tags: [conceptos, arquitectura, ha, cluster]
tipo: concepto
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Standalone vs Cluster Deployment

Viewtinet supports two primary deployment modes for its modules: standalone (single-node) and cluster (High Availability). Choosing the right mode depends on your availability requirements, hardware budget, and module type.

## Standalone Mode

In standalone mode, all services run on a single server. ViewtiSight, ViewtiManager, ViewtiAuth, and Viewticore are all installed together as part of the [[installation-bundle-steps|standard bundle installation]].

**When to use:**
- Development, test, or proof-of-concept environments
- Smaller deployments where downtime is acceptable
- [[viewtimon-overview|ViewtiMon]] (HA not supported — standalone only)
- [[viewtiqos-overview|ViewtiQoS]] (HA not supported — standalone only)

**Limitations:**
- Single point of failure
- No automatic failover
- Maintenance requires planned downtime

## Cluster (HA) Mode

In cluster mode, two or more nodes operate together with automatic failover. A floating Virtual IP (VIP) is managed by Keepalived, and HAProxy provides load balancing.

**When to use:**
- Production environments requiring continuous availability
- [[viewtilog-overview|ViewtiLog]] with high ingest volumes
- [[viewtisight-overview|ViewtiSight]] for uninterrupted analytics access

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
- NTP synchronization on all nodes — see [[system-configuration]]
- Each node requires its own license — see [[server-info]] and [[upload-license]]
- Dedicated inter-node network interface for heartbeat (recommended)

## Module HA Support Matrix

| Module | Standalone | Cluster/HA |
|---|---|---|
| ViewtiSight | Yes (default) | Yes — [[viewtisight-installation]] |
| ViewtiLog | Yes | Yes — [[viewtilog-installation]] |
| ViewtiMon | Yes | No — standalone only |
| ViewtiQoS | Yes | No — standalone only |

See [[ha-architecture]] for the broader HA architecture overview, and [[installation-guide-hub|Installation Guide Hub]] for source documentation.
