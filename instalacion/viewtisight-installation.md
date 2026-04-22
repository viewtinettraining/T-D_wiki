---
tags: [instalacion, viewtisight]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiSight Installation

ViewtiSight is installed automatically as part of the standard [[installation-bundle-steps|bundle installation]] alongside ViewtiManager and ViewtiAuth in standalone mode — there is no separate standalone installation step. This page focuses on the cluster (HA) deployment. For a product overview, see [[viewtisight-overview]].

## Standalone Deployment

In a [[standalone-vs-cluster|standalone deployment]], ViewtiSight, ViewtiManager, and Viewticore are all installed together during the [[installation-bundle-steps|three-step bundle installation]]. No additional steps are required for standalone mode.

## Cluster (HA) Installation

### Mandatory Requirements

- The primary node must be fully installed and licensed via the [[installation-bundle]]
- At least 2 nodes (one master, one mirror)
- A dedicated floating VIP address (e.g., `10.30.23.21`) managed by Keepalived
- NTP synchronization on all nodes — see [[system-configuration]]

### Recommended

- Homogeneous hardware (identical CPU, RAM, storage)
- Dedicated inter-node NIC for heartbeat and sync traffic
- Configure extra NICs via Netplan (`/etc/netplan/`) with static 10.100.x.x addresses

### Network Architecture

- Client traffic goes to the floating VIP
- Node 1 (eth0: `10.30.23.5`) handles traffic by default
- Node 2 (eth0: `10.30.23.6`) takes over on failover
- Heartbeat runs on a dedicated link (eth1: `10.100.100.100` ↔ `10.100.100.101`)

### Required Port Openings

For geographically distributed or firewalled clusters, open these ports between nodes:

| Component | Service Port | HA-Proxy Port |
|---|---|---|
| Viewtiauth-frontend-HTTP | 4600 | 4200 |
| Viewtisight-frontend-HTTP | 4602 | 8080 |
| Viewtisight-frontend-HTTPS | 4603 | 443 |
| Viewtimanager-frontend-HTTP | 4604 | 5000 |
| Viewticore-gateway | 8091 | 8090 |
| MongoDB (Viewtisight) | 23459 | N/A |

### Adding a Second Node

1. Log in to ViewtiManager on the master node: `http://MASTER-NODE-IP:4200/`
2. Click **Viewtisight** in the left navigation, then select the **Hosts** tab
3. Click **Add New Host**
4. Enter Node 2's management IP in "Hostname or IP Address" and its inter-node IP in "LAN Hostname or IP Address"
5. Enter Node 2's SSH credentials
6. Click **ADD NEW VIRTUAL ADDRESS** and enter the VIP
7. Click Save and confirm
8. Wait for the node's status indicator to turn Online/Healthy

### Licensing the Second Node

Each node requires its own license. Retrieve [[server-info]] from Node 2, request a `.key` file, then perform [[user-admin-activation]] and [[upload-license]] on Node 2.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
