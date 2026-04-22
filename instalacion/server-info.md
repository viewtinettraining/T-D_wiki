---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Server Info'
id: CBU-L3E-MEL-IAU
slug: server-info
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Server Info

Viewtinet uses a machine-unique identifier for licensing. This identifier is contained in the file `/opt/vn/viewtimanager/var/server-info.txt` on the target server.

## Purpose

The server-info.txt file provides Viewtinet with the hardware fingerprint needed to generate a license tied to that specific machine. This file must be shared with your Viewtinet representative before you can [upload a license](upload-license.md). Each node in a [cluster deployment](../conceptos/standalone-vs-cluster.md) requires its own license and therefore its own server-info.txt.

## How to Retrieve the File

### Using SCP (Linux)

```bash
scp viewtinet@<SERVER_IP>:/opt/vn/viewtimanager/var/server-info.txt .
```

### Using WinSCP (Windows)

1. Open WinSCP and connect using:
   - **Host:** IP address of the server
   - **Username:** `viewtinet`
   - **Password:** the password configured during [Os Setup](os-setup.md)
2. Navigate to `/opt/vn/viewtimanager/var/`
3. Download `server-info.txt` to your local machine

## Submitting for Licensing

Once downloaded, send the file by email to your Viewtinet representative. They will respond with a `.key` license file, which is then uploaded via the [Upload License](upload-license.md) procedure.

## Cluster Note

For [ViewtiSight cluster](viewtisight-installation.md) and [ViewtiLog cluster](viewtilog-installation.md) deployments, each additional node must be licensed separately. Retrieve the server-info.txt from each node individually before requesting licenses.

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full source index and [Installation Bundle](installation-bundle.md) for the surrounding installation context.
