---
tags: [instalacion, configuracion, sistema]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# System Configuration

This page describes the post-install system configuration steps required on [[ubuntu-compatibility|Ubuntu Server 20.04 or 24.04]] before proceeding with the [[installation-bundle|Viewtinet bundle installation]].

## User Profile Verification

All Viewtinet modules and containers run under the `viewtinet` user, which must have been created during [[os-setup|OS setup]]. The username cannot be changed — verify it is exactly `viewtinet` before proceeding.

## SSH Service

The OpenSSH server must be installed and enabled. If it was configured during OS installation, verify the service is running:

```bash
sudo systemctl status ssh
```

Password authentication over SSH must be allowed for bundle upload (SCP) and remote management.

## NTP Configuration

Correct time synchronization is critical for Viewtinet's clustering and logging features. Incorrect system time will cause issues in [[viewtilog-installation|ViewtiLog cluster]] and [[viewtisight-installation|ViewtiSight cluster]] deployments.

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

1. [[server-info]] — Obtain the server-info.txt for licensing
2. [[installation-bundle]] — Download, upload, and extract the installation bundle
3. [[installation-bundle-steps]] — Execute the three-step installation process

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
