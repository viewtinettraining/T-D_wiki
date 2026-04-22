---
tags: [configuracion, viewtimanager, actualizaciones]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# System Updates

ViewtiManager includes a built-in update mechanism that allows administrators to upgrade the entire [[viewtimanager-overview|Viewtinet platform]] — including all its modules — to the latest version provided by Viewtinet. Updates are applied from **Admin → Updates**.

> Important: This update process applies to the whole platform. It is not possible to update individual modules selectively using this method. For CLI-based update instructions, refer to the Viewtinet CLI Guide.

## Prerequisites

Before starting the update:

- Obtain the official update bundle (`.tgz` file) from Viewtinet Support.
- The bundle must be the latest supported version; the download link is provided by Viewtinet Support.

### Transferring the Bundle

Upload the `.tgz` bundle to the Viewtinet appliance using an SCP-capable tool such as WinSCP, FileZilla, or a terminal with `scp`:

1. Connect to the Viewtinet appliance (server or virtual machine).
2. Log in as a privileged user (typically `admin`).
3. Upload the `.tgz` file to: `/opt/vn/viewtimanager/updates/`

## Update Procedure

### 1. Open the Update Manager

- In the left sidebar, click **Admin**.
- Select the **Updates** tab.

### 2. Select the Bundle

- Click the dropdown arrow on **Bundles Available**.
- Choose the uploaded bundle file (e.g., `bundle-6.3.5-ubuntu20.04-20250716025138.tgz`).

### 3. Review Modules to Update

All modules detected in the bundle are listed. By default, every licensed module is checked:

- ViewtiManager, ViewtiSight, ViewtiAuth, ViewtiCore
- ViewtiMon & ViewtifyQoS
- [[viewtilog-overview|ViewtiLog]]

### 4. Start the Update

- Click **UPDATE** at the bottom and confirm the operation.
- A progress bar streams live console output as each module's packages and Docker images are deployed.

### 5. Finish Installation

- When bundle deployment completes, click **FINISH INSTALLATION**.
- Wait for the final confirmation.

### 6. Restart Each Module

After updating, each licensed and installed module must be restarted to apply the new version:

1. Select each module in the sidebar (e.g., ViewtiSight, ViewtiMon, ViewtifyQoS, ViewtiLog, Networking).
2. Click **RESTART** in the top-right corner and confirm.
3. Repeat for every updated module.

## Related Pages

- [[installation-bundle]] — Initial installation bundle overview
- [[installation-bundle-steps]] — Bundle installation steps
- [[license-management]] — License status after updates
- [[viewtimanager-overview]] — Full platform module overview
