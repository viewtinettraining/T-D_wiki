---
tags: [instalacion, viewtiqos]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiQoS Installation

ViewtiQoS (also referred to as Viewtify QoS) extends [[viewtimon-overview|ViewtiMon]]'s DPI capabilities into enterprise-grade traffic management. HA is not supported in the current release — only single-node deployment is available. For a product overview, see [[viewtiqos-overview]].

## Prerequisites

- [[viewtimon-installation|ViewtiMon must be installed and running]] on the target host
- The ViewtiQoS feature must be licensed and visible in the sidebar under **Viewtify QoS**
- [[upload-license|License activated]] with the Viewtify QoS entitlement

## Installation Procedure

### Launch the Installer

1. In ViewtiManager UI, click **Viewtify QoS** in the left navigation
2. Click **INSTALL QOS**

### Add the Cluster Host

1. Under **Cluster for QoS**, click **+ ADD NEW HOST**
2. Enter the management IP (e.g., `10.30.23.4`) in "Hostname or IP Address"
3. Enter the same IP in "LAN Hostname or IP Address"
4. Enter the SSH password for the `viewtinet` user in the Password fields
5. Click **SAVE CHANGES** and confirm the dialog

### Finish Installation

1. Wait for the installer log to stream and report **"Installation finished"**
2. Click **FINISH INSTALLATION**

## NIC Binding for QoS

ViewtiQoS requires exclusive NIC binding, which conflicts with ViewtiMon. Follow this sequence:

### Stop ViewtiMon

1. Navigate to **Viewtimon → STATUS**
2. Click **STOP** and confirm "Do you want to stop this module?" → **YES**

### Assign Interfaces

1. Go to **Networking → INTERFACES**
2. For each probe NIC to use with QoS, check the **Viewtify QoS** box
3. Click **SAVE CHANGES**

### Restart ViewtiMon

1. Return to **Viewtimon → STATUS**
2. Click **RESTART** (or START if still stopped)
3. Confirm → **YES**
4. Both [[viewtimon-overview|ViewtiMon]] and ViewtiQoS status indicators will turn green when active

ViewtiQoS is now installed. Traffic-shaping and prioritization policies can be configured via the Viewtify QoS interface.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
