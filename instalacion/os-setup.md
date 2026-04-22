---
tags: [instalacion, os, ubuntu]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Operating System Setup

This page covers the Ubuntu Server OS profile configuration required before installing Viewtinet. See [[ubuntu-compatibility]] for supported versions.

## Mandatory User Profile

All Viewtinet modules, containers, and services run under a dedicated system user named `viewtinet`. This user **must** be created during the Ubuntu Server installation with the exact username `viewtinet` — any deviation will prevent the platform from operating correctly.

During installation, when the **Profile setup** screen appears, complete the fields as follows:

| Field | Required Value |
|---|---|
| Your name | `viewtinet` |
| Your server's name | Any hostname (e.g., `my_viewtilog`) |
| Pick a username | `viewtinet` (mandatory) |
| Choose a password | A secure password per your org's policy |
| Confirm your password | Re-enter the password |

The hostname is at the administrator's discretion. The password must comply with your organization's security guidelines. The username, however, cannot be changed.

## SSH Configuration

During the OS installer's **SSH Setup** screen, enable remote management:

- Check: `[X] Install OpenSSH server`
- Set import identity to: `No`
- Check: `[X] Allow password authentication over SSH`

This configuration is mandatory for subsequent [[installation-bundle]] steps that rely on [[server-info]] retrieval and remote access via SCP or SSH tools such as WinSCP and PuTTY.

## Optional Packages

If the Ubuntu installer presents a "Featured Server Snaps" screen, **do not select any packages**. Installing additional packages at this stage may cause conflicts with Viewtinet modules. Click Done to proceed.

## Next Steps

After completing the OS profile setup, proceed to:

1. [[hdd-partitioning]] — Configure disk partitions according to the recommended scheme
2. [[system-configuration]] — Apply NTP and SSH post-install configuration
3. [[installation-bundle]] — Begin the Viewtinet bundle installation

See also [[installation-guide-hub|Installation Guide Hub]] for the full source index.
