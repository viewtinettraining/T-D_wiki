---
tags: [instalacion, bundle, procedimiento]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Installation Bundle Steps

This page details the three-step process for installing the Viewtinet platform from the [[installation-bundle|extracted bundle]]. Internet access is mandatory throughout all three steps.

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

1. [[user-admin-activation]] — Activate the admin user at `http://<SERVER_IP>:4200`
2. [[server-info]] — Retrieve the server-info.txt for licensing
3. [[upload-license]] — Upload the `.key` license file via [[viewtimanager-overview|ViewtiManager]]

## Module Installations

Once the base platform is running, install individual modules as needed:

- [[viewtilog-installation]] — ViewtiLog log management
- [[viewtimon-installation]] — ViewtiMon traffic monitoring
- [[viewtiqos-installation]] — ViewtiQoS traffic shaping
- [[viewtisight-installation]] — ViewtiSight analytics

See [[installation-guide-hub|Installation Guide Hub]] for the complete source index.
