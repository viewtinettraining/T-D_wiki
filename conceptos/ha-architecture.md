---
tags: [conceptos, ha, alta-disponibilidad, cluster, arquitectura]
tipo: tecnica
fuentes: ["HA Architecture 0619v2", "viewtinet-cli-guide_en_v6.3.5_v1.0"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# High Availability Architecture

The Viewtinet platform supports a High Availability (HA) deployment model for [[viewtisight-overview|ViewtiSight]] and [[viewtilog-overview|ViewtiLog]]. HA mode provides automatic failover, load balancing, and service continuity without manual intervention, making it the recommended deployment pattern for production environments.

## Active-Passive Model

Viewtinet HA follows an **active-passive** design:

- **Primary node (active)** — handles all traffic under normal conditions
- **Secondary node (passive/mirror)** — remains synchronized and ready to take over
- Failover is automatic; no operator action is required when the primary node fails

Both nodes run identical software stacks installed from the [[installation-bundle|installation bundle]] and must use homogeneous hardware (matching CPU, RAM, and storage is strongly recommended).

## Key Components

### Keepalived (VIP Management)

Keepalived manages the **Virtual IP (VIP)** — a floating IPv4 address that always points to the active node. External clients, the [[rest-api|REST API]], and the [[gui-overview|Viewtinet GUI]] all connect through the VIP, so they are unaffected by a node switch.

- VIP is configured during cluster installation
- Keepalived uses VRRP (Virtual Router Redundancy Protocol) to elect the active node
- On primary failure, the VIP migrates to the secondary node within seconds

### HAProxy (Load Balancing)

HAProxy sits in front of the cluster and distributes inbound connections across nodes. It performs health checks on each node and removes unhealthy nodes from the pool automatically.

HAProxy handles:
- HTTP and HTTPS traffic to [[viewtisight-overview|ViewtiSight]] (ports 8080, 443)
- API traffic to the [[rest-api|REST API]] gateway
- Internal service-to-service traffic in multi-node clusters

### Inter-Node Network Interface

A dedicated network interface is recommended for heartbeat traffic, state synchronization, and data replication between nodes. Mixing heartbeat with production traffic increases failover latency and risks false positives.

## Failover Process

1. Keepalived detects that the primary node is unreachable (missed heartbeats)
2. The secondary node promotes itself to active and claims the VIP
3. HAProxy routes all new connections to the now-active secondary
4. Existing sessions may be reset; clients reconnect transparently through the VIP

## Cluster Requirements

| Requirement | Detail |
|-------------|--------|
| Nodes | Minimum 2, identical hardware recommended |
| VIP | One floating IPv4 address per cluster |
| NTP | All nodes synchronized — see [[os-setup]] |
| Licenses | Each node requires its own license — see [[upload-license]] |
| Dedicated NIC | Separate interface for inter-node traffic (recommended) |

## Module HA Support

Not all Viewtinet modules support HA. See [[standalone-vs-cluster]] for the full matrix:

- [[viewtilog-overview|ViewtiLog]] — HA supported
- [[viewtisight-overview|ViewtiSight]] — HA supported
- [[viewtimon-overview|ViewtiMon]] — standalone only
- [[viewtiqos-overview|ViewtiQoS]] — standalone only

## CLI Tools for HA

The [[cli-reference|CLI]] provides scripts to check HA status:

- `check_vrrp.sh` — shows current VRRP state and VIP ownership
- `check_ip.sh` — verifies IP binding on each node
- `troubleshooting.sh` — comprehensive health diagnostic including HA state

These scripts are located in `/opt/vn/viewtinet-builder/scripts/`.
