---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Installation Bundle Steps'
id: LPK-AFP-BA7-E5Y
slug: installation-bundle-steps
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Installation Bundle Steps

This page details the three-step process for installing the Viewtinet platform from the [extracted bundle](installation-bundle.md). Internet access is mandatory throughout all three steps.

## Step 1 — Deploy (deploy.sh)

Navigate into the bundle directory and run the deploy script:

```bash
cd bundle/
./deploy.sh
```

If prompted for the `viewtinet` user password, enter `viewtinet` (without quotes).

The script bootstraps the environment. At the end you will see output including a line like `Unpacking viewtinet-builder (6.3.x)`. The exact version number may differ from examples in the documentation.

## Step 2 — Install Dependencies (install.sh, first run)

Run the installer script to install all system dependencies:

```bash
/opt/vn/viewtinet-builder/install.sh
```

This step installs Docker and all other required packages. At the end, the script instructs you to **log out and log back in** before continuing. Close the SSH/PuTTY session completely and reconnect before proceeding to Step 3.

## Step 3 — Load Images and Configure (install.sh, second run)

After reconnecting via SSH, run the same installer script again:

```bash
/opt/vn/viewtinet-builder/install.sh
```

This second run loads the container images, configures internal networking, sets up port forwarding, and completes the full deployment. When finished, an installation completion message confirms success.

## Post-Installation

After all three steps complete:

1. [User Admin Activation](user-admin-activation.md) — Activate the admin user at `http://<SERVER_IP>:4200`
2. [Server Info](server-info.md) — Retrieve the server-info.txt for licensing
3. [Upload License](upload-license.md) — Upload the `.key` license file via [ViewtiManager](../productos/viewtimanager-overview.md)

## Module Installations

Once the base platform is running, install individual modules as needed:

- [Viewtilog Installation](viewtilog-installation.md) — ViewtiLog log management
- [Viewtimon Installation](viewtimon-installation.md) — ViewtiMon traffic monitoring
- [Viewtiqos Installation](viewtiqos-installation.md) — ViewtiQoS traffic shaping
- [Viewtisight Installation](viewtisight-installation.md) — ViewtiSight analytics

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the complete source index.
