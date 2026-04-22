---
tags: [instalacion, viewtilog]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiLog Installation

This page covers both standalone and cluster (High-Availability) installation modes for ViewtiLog. For a conceptual overview of the product, see [[viewtilog-overview]].

## Prerequisites

- A running [[viewtimanager-overview|ViewtiManager]] instance with admin GUI access
- SSH credentials for the target host (the `viewtinet` user password)
- [[upload-license|License activated]] with the ViewtiLog feature enabled
- Network connectivity between browser and ViewtiManager

For HA clusters, NTP synchronization across all nodes is mandatory — see [[system-configuration]].

## Standalone Installation

Standalone mode deploys ViewtiLog on the same host as ViewtiManager using Docker containers.

1. Log in to ViewtiManager as **admin**
2. Click **Viewtilog** in the left navigation menu
3. Click **Install Connectors**
4. Under **Cluster for Connectors**, click **+ Add New Host**
5. Enter the same IP address in both the "Hostname or IP Address" and "LAN Hostname or IP Address" fields (standalone uses the same address for both)
6. Enter the SSH password for the `viewtinet` user in the Password fields
7. Click **Save Changes** and confirm in the dialog
8. Wait for the installation log to complete and display the success message
9. Click **Finish Installation**

Result: ViewtiLog is installed and available to run ETL tasks.

## Cluster (HA) Installation

See [[standalone-vs-cluster]] for an overview of the differences. Cluster mode requires at least two nodes with a floating Virtual IP (VIP) managed by Keepalived and load-balanced by HAProxy.

### Additional HA Requirements

- At least 2 nodes (one master, one mirror)
- A dedicated floating VIP address (e.g., `10.30.23.21`)
- Dedicated inter-node NIC for heartbeat/sync traffic (recommended)
- Homogeneous hardware across nodes
- NTP synchronized on all nodes

### Adding a Second Node

1. Log in to ViewtiManager via the VIP: `http://VIP-IP:4200/`
2. Navigate to **Viewtilog → Hosts** tab
3. Click **Add New Host**
4. Enter Node 2's management IP in "Hostname or IP Address" and its inter-node IP in "LAN Hostname or IP Address"
5. Enter Node 2's SSH credentials
6. Click **Add New Virtual Address** and enter the VIP (e.g., `10.30.23.21`)
7. Click Save and confirm
8. Wait for "Installation Finished"

Each cluster node requires its own license. Retrieve [[server-info]] from each node and obtain separate `.key` files.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
