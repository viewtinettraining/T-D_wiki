---
title: "Installation Bundle"
description: "The Viewtinet installation bundle is the primary delivery mechanism for the Viewtinet platform. It is a `.zip` archive containing all required scripts, conta..."
keywords: "instalacion, bundle"
---

# Installation Bundle

The Viewtinet installation bundle is the primary delivery mechanism for the Viewtinet platform. It is a `.zip` archive containing all required scripts, container images, and configuration files needed to deploy the full stack on [Ubuntu Server 20.04 or 24.04](../conceptos/ubuntu-compatibility.md).

## Prerequisites

Before working with the bundle, ensure the following are complete:

- [Os Setup](os-setup.md) — `viewtinet` user created, OS profile configured
- [Hdd Partitioning](hdd-partitioning.md) — Disk partitions created per the recommended scheme
- [System Configuration](system-configuration.md) — SSH enabled, NTP configured and synchronized

Internet access is **mandatory** during installation — all dependencies and Docker images are downloaded at runtime.

## Downloading the Bundle

Your Viewtinet representative provides a download link for the `artifacts.zip` file. Download and store it locally before proceeding.

## Uploading the Bundle

Upload the bundle to `/home/viewtinet` on the target server.

**From Linux:**
```bash
scp artifacts.zip viewtinet@<SERVER_IP>:/home/viewtinet
```

**From Windows (WinSCP):**
1. Open WinSCP, enter the server IP, username `viewtinet`, and the OS password
2. Navigate to the local folder containing `artifacts.zip`
3. Upload to `/home/viewtinet` on the server

## SSH Connection

If working remotely, connect via SSH before running installation commands.

**Using PuTTY:**
1. Enter the server IP in the Host Name field
2. Click Open and log in as `viewtinet`

## Extracting the Bundle

```bash
# Install unzip if needed
sudo apt install unzip

# Navigate to the upload directory
cd /home/viewtinet

# Extract
unzip artifacts.zip
```

After extraction, a `bundle/` directory is created. All three installation steps are run from within this directory — see [Installation Bundle Steps](installation-bundle-steps.md) for details.

## Related Pages

- [Server Info](server-info.md) — Obtain machine identifier for licensing
- [User Admin Activation](user-admin-activation.md) — First-login admin activation
- [Upload License](upload-license.md) — Upload the .key license file
- [Installation Guide Hub](../fuentes/installation-guide-hub.md) — Full source index
