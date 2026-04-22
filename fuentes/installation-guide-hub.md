---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Installation Guide Hub'
id: QRR-B8S-4NT-ZLC
slug: installation-guide-hub
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Installation Guide Hub

This page summarizes the full Installation Guide section of the Viewtinet documentation hub and links to all individual source files and the derived wiki pages.

## Overview

The Installation Guide covers the complete lifecycle of a Viewtinet deployment: from hardware preparation and operating system setup, through bundle installation and licensing, to module-specific installations for [ViewtiLog](../productos/viewtilog-overview.md), [ViewtiMon](../productos/viewtimon-overview.md), [ViewtiQoS](../productos/viewtiqos-overview.md), and [ViewtiSight](../productos/viewtisight-overview.md).

Compatibility is limited to [Ubuntu Server 20.04 LTS and 24.04 LTS](../conceptos/ubuntu-compatibility.md). All procedures assume the operating system is already installed and partitioned. The installation model supports both [standalone and cluster deployments](../conceptos/standalone-vs-cluster.md).

## Source Files Index

### Introduction
- [about-installation-guide.md](about-installation-guide.md) — Disclaimers, audience, and supported OS matrix

### OS Configurations
- [operating-system-setup.md](../instalacion/os-setup.md) — Ubuntu user profile setup (viewtinet user)
- [hdd-partitioning.md](../instalacion/hdd-partitioning.md) — Recommended RAID and partition layout
- [system-configuration.md](../instalacion/system-configuration.md) — SSH, NTP, and post-install configuration

### Bundle Installation
- [getting-server-info.md](../instalacion/server-info.md) — Obtaining the server-info.txt for licensing
- [preparing-the-installation-bundle.md](preparing-the-installation-bundle.md) — Download, upload, and extract the .zip bundle
- [installation-step1.md](installation-step1.md) — Step 1: run deploy.sh
- [installation-step2.md](installation-step2.md) — Step 2: run install.sh and re-login
- [installation-step3.md](installation-step3.md) — Step 3: run install.sh again (images + config)
- [upload-license.md](../instalacion/upload-license.md) — Upload the .key license file via the GUI
- [user-admin-activation.md](../instalacion/user-admin-activation.md) — First-login admin password activation

### Module Installations
- [about-viewtilog.md](about-viewtilog.md) — ViewtiLog overview
- [standalone-installation.md (viewtilog)](standalone-installation (viewtilog).md) — ViewtiLog standalone installation
- [cluster-installation.md (viewtilog)](cluster-installation (viewtilog).md) — ViewtiLog HA cluster installation
- [about-viewtimon.md](about-viewtimon.md) — ViewtiMon overview and NIC requirements
- [standalone-installation.md (viewtimon)](standalone-installation (viewtimon).md) — ViewtiMon standalone installation
- [fine-tuning.md](fine-tuning.md) — ViewtiMon kernel and CPU fine-tuning
- [about-viewtify-qos.md](about-viewtify-qos.md) — ViewtiQoS overview
- [standalone-installation.md (viewtiqos)](standalone-installation (viewtiqos).md) — ViewtiQoS installation
- [about-viewtilog-guide-installation.md](about-viewtilog-guide-installation.md) — ViewtiSight overview
- [cluster-installation.md (viewtisight)](cluster-installation (viewtisight).md) — ViewtiSight cluster installation

### Appliance
- [getting-to-know-your-appliance.md](getting-to-know-your-appliance.md) — Physical ports and hardware layout
- [how-to-rack-your-appliance.md](how-to-rack-your-appliance.md) — Rail assembly and rack mounting procedure
- [ipmi-ip-address-configuration.md](../conceptos/ipmi-management.md) — BIOS-level IPMI IP setup
- [managing-your-appliance-via-ipmi.md](managing-your-appliance-via-ipmi.md) — Web-based IPMI remote console
- [changing-the-management-ip-address.md](changing-the-management-ip-address.md) — Script-based management IP change

## Derived Wiki Pages

| Topic | Wiki Page |
|---|---|
| OS Setup | [Os Setup](../instalacion/os-setup.md) |
| HDD Partitioning | [Hdd Partitioning](../instalacion/hdd-partitioning.md) |
| System Configuration | [System Configuration](../instalacion/system-configuration.md) |
| Server Info | [Server Info](../instalacion/server-info.md) |
| Installation Bundle | [Installation Bundle](../instalacion/installation-bundle.md) |
| Bundle Steps | [Installation Bundle Steps](../instalacion/installation-bundle-steps.md) |
| License Upload | [Upload License](../instalacion/upload-license.md) |
| Admin Activation | [User Admin Activation](../instalacion/user-admin-activation.md) |
| ViewtiLog Installation | [Viewtilog Installation](../instalacion/viewtilog-installation.md) |
| ViewtiMon Installation | [Viewtimon Installation](../instalacion/viewtimon-installation.md) |
| ViewtiQoS Installation | [Viewtiqos Installation](../instalacion/viewtiqos-installation.md) |
| ViewtiSight Installation | [Viewtisight Installation](../instalacion/viewtisight-installation.md) |
| ViewtiLog Overview | [Viewtilog Overview](../productos/viewtilog-overview.md) |
| ViewtiMon Overview | [Viewtimon Overview](../productos/viewtimon-overview.md) |
| ViewtiQoS Overview | [Viewtiqos Overview](../productos/viewtiqos-overview.md) |
| ViewtiSight Overview | [Viewtisight Overview](../productos/viewtisight-overview.md) |
| Appliance | [Viewtinet Appliance](../productos/viewtinet-appliance.md) |
| Ubuntu Compatibility | [Ubuntu Compatibility](../conceptos/ubuntu-compatibility.md) |
| Standalone vs Cluster | [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md) |
| IPMI Management | [Ipmi Management](../conceptos/ipmi-management.md) |
