---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Viewtinet Appliance'
id: KVZ-02Y-QKR-YFB
slug: viewtinet-appliance
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Viewtinet Appliance

The Viewtinet appliance is a purpose-built hardware platform designed to run the Viewtinet software stack, including [ViewtiMon](viewtimon-overview.md) and [ViewtiQoS](viewtiqos-overview.md). It ships with a default management IP that must be updated before deployment.

## Physical Layout

### Rear Panel Ports

1. Power Supply (primary)
2. Power Supply (redundant)
3. Management Interface (network)
4. Serial Port for monitor
5. **IPMI Interface** (out-of-band management) — see [Ipmi Management](../conceptos/ipmi-management.md)
6. USB Ports (keyboard or bypass)

## Racking the Appliance

The appliance ships with a rail assembly kit containing inner rails, middle rails, and outer rails.

**Warning:** Do not carry the server using the front handles — they are designed only for pulling the chassis from a rack.

### Procedure Summary

1. Extend the inner rail from the outer rail until fully extended, then press the locking tab to release it
2. Attach the inner rails to the chassis sides, aligning hooks with chassis holes, and slide forward until locked; secure with screws
3. Mount the outer rails to the rack posts, adjusting length to fit the rack depth
4. Align the chassis inner rails with the front of the middle rails and slide in until the locking tab clicks
5. Depress locking tabs on both sides simultaneously and push the chassis fully into the rack

## Changing the Management IP

The appliance ships with a default management IP. To change it, use the dedicated script — changing the OS IP alone is not sufficient because multiple internal services and containers depend on the management IP.

```bash
/opt/vn/viewtinet-builder/scripts/change-management-ip.sh
```

The script prompts for IPMI access confirmation, then for current and new IP/mask/gateway values. It updates Netplan configuration, all component `.env` files, and MongoDB, then restarts affected services. Finalize with:

```bash
sudo netplan apply
```

After the IP change, use the new IP for both SSH and [GUI](../configuracion/gui-overview.md) access. Confirm [IPMI access](../conceptos/ipmi-management.md) is available before running this script — if the process fails, IPMI provides recovery access.

## IPMI Configuration

IPMI is configured via the BIOS Setup Utility at boot. See [Ipmi Management](../conceptos/ipmi-management.md) for the full IPMI setup and remote console procedures.

## Software Installation

After physical setup and IP configuration, proceed with [Os Setup](../instalacion/os-setup.md), [Hdd Partitioning](../instalacion/hdd-partitioning.md), [System Configuration](../instalacion/system-configuration.md), and [Installation Bundle](../instalacion/installation-bundle.md) to deploy the Viewtinet software.

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full source index.
