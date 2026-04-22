---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'ViewtiMon Overview'
id: 53V-6CW-5Z3-FIX
slug: viewtimon-overview
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# ViewtiMon Overview

ViewtiMon is the high-performance traffic monitoring engine of the Viewtinet platform. It uses Deep Packet Inspection (DPI) and scalable probe architectures to deliver real-time visibility into application usage, network performance, and end-user experience.

## Purpose

ViewtiMon is deployed on Viewtinet's purpose-built appliances (or certified hardware with approved NICs). It provides the raw traffic intelligence that feeds the entire Viewtinet analytics stack — including [ViewtiSight](viewtisight-overview.md) for reporting and [ViewtiQoS](viewtiqos-overview.md) for traffic management.

## Key Capabilities

- **Application Recognition** — DPI-based classification identifies thousands of applications and protocols, including those on non-standard ports or encrypted traffic
- **QoE and Network KPIs** — Continuously measures Quality of Experience, latency, jitter, packet loss, and throughput for voice, video, and business-critical applications
- **North-South and East-West Monitoring** — Full-mesh flow analysis covering both internet/WAN traffic and internal data-center (East-West) traffic
- **Remote Site Scalability** — Flexible deployment options from high-density enterprise probes to lightweight collectors for small branch offices

## Certified Network Interfaces

ViewtiMon is certified on the following NICs only:

| NIC | Model |
|---|---|
| Intel | Ethernet Controller X710 for 10 GbE SFP+ 1572 (Preferred) |
| Mellanox | MT27710 Family ConnectX-4 LX |
| Mellanox | ConnectX-5 LX |
| Cisco | VIC Ethernet NIC |

## Operational Benefits

ViewtiMon's real-time analytics enable teams to:
- Troubleshoot performance bottlenecks
- Enforce application-aware policies
- Detect and respond to anomalies
- Plan capacity and forecast growth

## Integration

ViewtiMon data feeds into [ViewtiSight](viewtisight-overview.md) for visualization, alarms, and long-term reporting. It is a prerequisite for [ViewtiQoS](viewtiqos-overview.md) deployment.

HA is not supported for ViewtiMon — only [standalone deployment](../conceptos/standalone-vs-cluster.md) is available. See [Viewtimon Installation](../instalacion/viewtimon-installation.md) for installation steps and fine-tuning details.

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for related source documentation.
