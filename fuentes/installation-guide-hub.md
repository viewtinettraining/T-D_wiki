---
tags: [instalacion, fuente]
tipo: fuente
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Installation Guide Hub

This page summarizes the full Installation Guide section of the Viewtinet documentation hub and links to all individual source files and the derived wiki pages.

## Overview

The Installation Guide covers the complete lifecycle of a Viewtinet deployment: from hardware preparation and operating system setup, through bundle installation and licensing, to module-specific installations for [[viewtilog-overview|ViewtiLog]], [[viewtimon-overview|ViewtiMon]], [[viewtiqos-overview|ViewtiQoS]], and [[viewtisight-overview|ViewtiSight]].

Compatibility is limited to [[ubuntu-compatibility|Ubuntu Server 20.04 LTS and 24.04 LTS]]. All procedures assume the operating system is already installed and partitioned. The installation model supports both [[standalone-vs-cluster|standalone and cluster deployments]].

## Source Files Index

### Introduction
- [[about-installation-guide|about-installation-guide.md]] — Disclaimers, audience, and supported OS matrix

### OS Configurations
- [[os-setup|operating-system-setup.md]] — Ubuntu user profile setup (viewtinet user)
- [[hdd-partitioning|hdd-partitioning.md]] — Recommended RAID and partition layout
- [[system-configuration|system-configuration.md]] — SSH, NTP, and post-install configuration

### Bundle Installation
- [[server-info|getting-server-info.md]] — Obtaining the server-info.txt for licensing
- [[preparing-the-installation-bundle|preparing-the-installation-bundle.md]] — Download, upload, and extract the .zip bundle
- [[installation-step1|installation-step1.md]] — Step 1: run deploy.sh
- [[installation-step2|installation-step2.md]] — Step 2: run install.sh and re-login
- [[installation-step3|installation-step3.md]] — Step 3: run install.sh again (images + config)
- [[upload-license|upload-license.md]] — Upload the .key license file via the GUI
- [[user-admin-activation|user-admin-activation.md]] — First-login admin password activation

### Module Installations
- [[about-viewtilog|about-viewtilog.md]] — ViewtiLog overview
- [[standalone-installation (viewtilog)|standalone-installation.md (viewtilog)]] — ViewtiLog standalone installation
- [[cluster-installation (viewtilog)|cluster-installation.md (viewtilog)]] — ViewtiLog HA cluster installation
- [[about-viewtimon|about-viewtimon.md]] — ViewtiMon overview and NIC requirements
- [[standalone-installation (viewtimon)|standalone-installation.md (viewtimon)]] — ViewtiMon standalone installation
- [[fine-tuning|fine-tuning.md]] — ViewtiMon kernel and CPU fine-tuning
- [[about-viewtify-qos|about-viewtify-qos.md]] — ViewtiQoS overview
- [[standalone-installation (viewtiqos)|standalone-installation.md (viewtiqos)]] — ViewtiQoS installation
- [[about-viewtilog-guide-installation|about-viewtilog-guide-installation.md]] — ViewtiSight overview
- [[cluster-installation (viewtisight)|cluster-installation.md (viewtisight)]] — ViewtiSight cluster installation

### Appliance
- [[getting-to-know-your-appliance|getting-to-know-your-appliance.md]] — Physical ports and hardware layout
- [[how-to-rack-your-appliance|how-to-rack-your-appliance.md]] — Rail assembly and rack mounting procedure
- [[ipmi-management|ipmi-ip-address-configuration.md]] — BIOS-level IPMI IP setup
- [[managing-your-appliance-via-ipmi|managing-your-appliance-via-ipmi.md]] — Web-based IPMI remote console
- [[changing-the-management-ip-address|changing-the-management-ip-address.md]] — Script-based management IP change

## Derived Wiki Pages

| Topic | Wiki Page |
|---|---|
| OS Setup | [[os-setup]] |
| HDD Partitioning | [[hdd-partitioning]] |
| System Configuration | [[system-configuration]] |
| Server Info | [[server-info]] |
| Installation Bundle | [[installation-bundle]] |
| Bundle Steps | [[installation-bundle-steps]] |
| License Upload | [[upload-license]] |
| Admin Activation | [[user-admin-activation]] |
| ViewtiLog Installation | [[viewtilog-installation]] |
| ViewtiMon Installation | [[viewtimon-installation]] |
| ViewtiQoS Installation | [[viewtiqos-installation]] |
| ViewtiSight Installation | [[viewtisight-installation]] |
| ViewtiLog Overview | [[viewtilog-overview]] |
| ViewtiMon Overview | [[viewtimon-overview]] |
| ViewtiQoS Overview | [[viewtiqos-overview]] |
| ViewtiSight Overview | [[viewtisight-overview]] |
| Appliance | [[viewtinet-appliance]] |
| Ubuntu Compatibility | [[ubuntu-compatibility]] |
| Standalone vs Cluster | [[standalone-vs-cluster]] |
| IPMI Management | [[ipmi-management]] |
