---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Ubuntu Upgrade: 20.04 to 24.04'
id: ISN-09T-AH1-W3W
slug: ubuntu-upgrade
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Ubuntu Upgrade: 20.04 to 24.04

This page documents the two-stage procedure for upgrading a Viewtinet appliance from Ubuntu 20.04 LTS to Ubuntu 24.04 LTS. A direct upgrade path does not exist; the upgrade must pass through Ubuntu 22.04 LTS as an intermediate step.

For the supported OS versions in Viewtinet, see [Ubuntu Compatibility](../conceptos/ubuntu-compatibility.md). For initial OS configuration after a fresh install, see [Os Setup](os-setup.md).

> **Requirement**: IPMI access or direct physical access to the appliance is mandatory. The upgrade cannot be completed without it.

## Overview

| Stage | From | To |
|---|---|---|
| Stage 1 | Ubuntu 20.04 LTS | Ubuntu 22.04 LTS |
| Stage 2 | Ubuntu 22.04 LTS | Ubuntu 24.04 LTS |

---

## Stage 1: Ubuntu 20.04 to 22.04

### 1.1 Backup

Complete a full backup of all data and configuration files before proceeding.

### 1.2 Firewall Rules

Open the following outbound connections on your firewall:
- `https://repo.mongodb.org/apt/ubuntu`
- `http://es.archive.ubuntu.com/ubuntu`
- `http://security.ubuntu.com/ubuntu`
- `https://ppa.launchpadcontent.net/deadsnakes/ppa/ubuntu/`
- `https://changelogs.ubuntu.com/meta-release-lts`

### 1.3 Session Access

Use IPMI (preferred) or SSH. If using SSH, open a `screen` session to prevent disconnection:

```bash
screen -S UPGRADE
```

### 1.4 System Update

```bash
sudo apt update
sudo apt upgrade
sudo apt autoremove
```

When prompted to restart Docker automatically, answer **No**.

### 1.5 Configure Update Manager

Edit `/etc/update-manager/release-upgrades` and verify the line reads:

```
Prompt=lts
```

This restricts upgrades to LTS releases only.

### 1.6 Initiate the Upgrade

```bash
sudo do-release-upgrade
```

If prompted about a pending reboot before upgrading, reboot first and reopen the screen session. If using SSH, answer **Yes** when asked to open port 1022 for the upgrade (open it on the firewall if `ufw` is active).

During the upgrade, answer the prompts as follows:

| Prompt | Answer |
|---|---|
| Start the upgrade? | Yes |
| Restart services automatically? | No |
| Postfix configuration | No Configuration |
| Allow non-superusers to capture packets? | No |
| Change timesyncd configuration file? | N |
| Change sysctl configuration file? | N |
| Restart Docker automatically? | No |
| Remove obsolete packages? | y |
| Restart system now? | Yes |

### 1.7 Verify Stage 1

After reboot:

```bash
cat /etc/issue
```

Expected output: `Ubuntu 22.04.5 LTS \n \l`

---

## Stage 2: Ubuntu 22.04 to 24.04

### 2.1 Backup and Firewall

No additional backup or firewall changes are required beyond those from Stage 1.

### 2.2 System Update

```bash
sudo apt update
sudo apt upgrade
sudo apt autoremove
```

### 2.3 Configure Update Manager

Verify `/etc/update-manager/release-upgrades` still contains `Prompt=lts`.

### 2.4 Initiate the Upgrade

```bash
sudo do-release-upgrade
```

Follow the same prompt answers as Stage 1 (see table above). Allow port 1022 if prompted over SSH.

### 2.5 Interface Naming Change

Ubuntu 24.04 changes network interface naming conventions. Interfaces that previously used names like `enp67s0f0` are renamed to `enp67s0f0np0`. This may cause interfaces to go down after reboot.

**Fix:**

1. List current interface names:
   ```bash
   ip addr | grep -v link | grep mtu
   ```
2. Edit the netplan configuration:
   ```bash
   sudo nano /etc/netplan/00-installer-config.yaml
   ```
   Replace old interface names with the new `npX`-suffixed names.
3. Apply the configuration:
   ```bash
   sudo netplan generate
   sudo netplan apply
   ```

### 2.6 Final Package Updates

```bash
sudo apt update
sudo apt upgrade
sudo apt autoremove
```

Install Python 3.8 and pip (not included by default in Ubuntu 24.04):

```bash
sudo add-apt-repository -y ppa:deadsnakes/ppa
sudo apt install -y python3.8
sudo apt install -y python3-pip
```

### 2.7 Verify Stage 2

```bash
cat /etc/issue
```

Expected output: `Ubuntu 24.04 LTS \n \l`

---

After completing both stages, the appliance is running Ubuntu 24.04 LTS. Verify that all Viewtinet services are operational. For [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) deployments, perform the upgrade on each node sequentially. For [Ha Architecture](../conceptos/ha-architecture.md) clusters, coordinate maintenance windows accordingly.
