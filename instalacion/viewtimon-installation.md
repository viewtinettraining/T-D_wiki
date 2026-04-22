---
tags: [instalacion, viewtimon]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiMon Installation

This page covers the standalone installation of ViewtiMon and the performance fine-tuning steps required after installation. For a product overview, see [[viewtimon-overview]]. HA is not supported for ViewtiMon in the current release.

## Prerequisites

- [[viewtimanager-overview|ViewtiManager]] running with ViewtiMon licensed and visible in the sidebar
- An approved NIC (Intel X710, Mellanox ConnectX-4 LX, ConnectX-5 LX, or Cisco VIC)
- Sufficient disk space at `/opt/vn/probe/var/` (600 GB recommended — see [[hdd-partitioning]])

## Standalone Installation

1. Log in to ViewtiManager as admin (or a user with install privileges)
2. Click **Viewtimon** in the left navigation
3. Click **INSTALL VIEWTIMON**
4. Under **Cluster for Viewtimon**, click **+ ADD NEW HOST**
5. Enter the management IP in "Hostname or IP Address" and the same IP in "LAN Hostname or IP Address"
6. Enter the SSH password for the `viewtinet` user
7. Click **SAVE CHANGES** and confirm the dialog
8. Wait for "Installation finished" in the log stream
9. Click **FINISH INSTALLATION**

### Assigning Traffic Interfaces

1. Navigate to **Networking → INTERFACES**
2. For each NIC to be used for traffic monitoring, check the **Viewtimon** box (do not enable HA)
3. Click **SAVE CHANGES** and acknowledge the restart banner

### Starting the Service

1. Go to **Viewtimon → STATUS**
2. Click **START** and confirm "Do you want to start this module?" → **YES**
3. The status indicator turns green when ViewtiMon is active

## Fine-Tuning for Performance

To maximize throughput, apply the following kernel-level tunings before or after installation.

### HPET (High Precision Event Timer)

```bash
cat /sys/devices/system/clocksource/clocksource0/available_clocksource
```

If `hpet` appears, enable it in GRUB by appending `clocksource=hpet` to `GRUB_CMDLINE_LINUX_DEFAULT`, then run `sudo update-grub` and reboot.

### Hugepages (1 GB recommended)

Verify CPU support with `cat /proc/cpuinfo | egrep -o pdpe1gb | head -n1`. Configure the count based on NUMA nodes and RAM, then add to GRUB and mount the hugetlbfs:

```bash
echo "nodev /mnt/huge_1GB hugetlbfs pagesize=1GB 0 0" | sudo tee -a /etc/fstab
sudo mkdir -p /mnt/huge_1GB
sudo mount -a
```

### CPU Isolation

Use the helper script to compute the required CPU count:

```bash
sudo /opt/vn/viewtinet-builder/scripts/compute-isolated-cpus.sh
```

Then set `isolcpus`, `nohz_full`, and `rcu_nocbs` in GRUB accordingly. Reboot to apply all kernel parameters.

For [[viewtiqos-installation|ViewtiQoS]] deployment, ViewtiMon must be stopped before NIC binding for QoS.

See [[installation-guide-hub|Installation Guide Hub]] for the full source index.
