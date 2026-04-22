---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'System Configuration'
id: F7J-XSA-WZU-DQ1
slug: system-configuration
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# System Configuration

This page describes the post-install system configuration steps required on [Ubuntu Server 20.04 or 24.04](../conceptos/ubuntu-compatibility.md) before proceeding with the [Viewtinet bundle installation](installation-bundle.md).

## User Profile Verification

All Viewtinet modules and containers run under the `viewtinet` user, which must have been created during [OS setup](os-setup.md). The username cannot be changed — verify it is exactly `viewtinet` before proceeding.

## SSH Service

The OpenSSH server must be installed and enabled. If it was configured during OS installation, verify the service is running:

```bash
sudo systemctl status ssh
```

Password authentication over SSH must be allowed for bundle upload (SCP) and remote management.

## NTP Configuration

Correct time synchronization is critical for Viewtinet's clustering and logging features. Incorrect system time will cause issues in [ViewtiLog cluster](viewtilog-installation.md) and [ViewtiSight cluster](viewtisight-installation.md) deployments.

### Install and configure NTP

```bash
sudo apt-get install ntp
sudo vi /etc/ntp.conf
```

Add NTP servers in the `# Specify one or more NTP servers` section. Use customer-provided NTP servers, or select public servers from https://support.ntp.org/bin/view/Servers/NTPPoolServers for your region.

### Restart and verify

```bash
sudo service ntp restart
sudo service ntp status
sudo systemctl status systemd-timesyncd
timedatectl
```

Expected output confirming synchronization:

```
System clock synchronized: yes
NTP service: active
```

## Next Steps

Once SSH and NTP are confirmed operational, proceed to:

1. [Server Info](server-info.md) — Obtain the server-info.txt for licensing
2. [Installation Bundle](installation-bundle.md) — Download, upload, and extract the installation bundle
3. [Installation Bundle Steps](installation-bundle-steps.md) — Execute the three-step installation process

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full source index.
