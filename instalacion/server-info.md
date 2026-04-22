---
tags: [instalacion, licencias]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Server Info

Viewtinet uses a machine-unique identifier for licensing. This identifier is contained in the file `/opt/vn/viewtimanager/var/server-info.txt` on the target server.

## Purpose

The server-info.txt file provides Viewtinet with the hardware fingerprint needed to generate a license tied to that specific machine. This file must be shared with your Viewtinet representative before you can [[upload-license|upload a license]]. Each node in a [[standalone-vs-cluster|cluster deployment]] requires its own license and therefore its own server-info.txt.

## How to Retrieve the File

### Using SCP (Linux)

```bash
scp viewtinet@<SERVER_IP>:/opt/vn/viewtimanager/var/server-info.txt .
```

### Using WinSCP (Windows)

1. Open WinSCP and connect using:
   - **Host:** IP address of the server
   - **Username:** `viewtinet`
   - **Password:** the password configured during [[os-setup]]
2. Navigate to `/opt/vn/viewtimanager/var/`
3. Download `server-info.txt` to your local machine

## Submitting for Licensing

Once downloaded, send the file by email to your Viewtinet representative. They will respond with a `.key` license file, which is then uploaded via the [[upload-license]] procedure.

## Cluster Note

For [[viewtisight-installation|ViewtiSight cluster]] and [[viewtilog-installation|ViewtiLog cluster]] deployments, each additional node must be licensed separately. Retrieve the server-info.txt from each node individually before requesting licenses.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index and [[installation-bundle]] for the surrounding installation context.
