---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Operating System Setup'
id: U3M-DM1-VED-4Z6
slug: os-setup
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Operating System Setup

This page covers the Ubuntu Server OS profile configuration required before installing Viewtinet. See [Ubuntu Compatibility](../conceptos/ubuntu-compatibility.md) for supported versions.

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

This configuration is mandatory for subsequent [Installation Bundle](installation-bundle.md) steps that rely on [Server Info](server-info.md) retrieval and remote access via SCP or SSH tools such as WinSCP and PuTTY.

## Optional Packages

If the Ubuntu installer presents a "Featured Server Snaps" screen, **do not select any packages**. Installing additional packages at this stage may cause conflicts with Viewtinet modules. Click Done to proceed.

## Next Steps

After completing the OS profile setup, proceed to:

1. [Hdd Partitioning](hdd-partitioning.md) — Configure disk partitions according to the recommended scheme
2. [System Configuration](system-configuration.md) — Apply NTP and SSH post-install configuration
3. [Installation Bundle](installation-bundle.md) — Begin the Viewtinet bundle installation

See also [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full source index.
