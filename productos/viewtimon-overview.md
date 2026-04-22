---
tags: [productos, viewtimon, monitoreo, dpi]
tipo: concepto
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiMon Overview

ViewtiMon is the high-performance traffic monitoring engine of the Viewtinet platform. It uses Deep Packet Inspection (DPI) and scalable probe architectures to deliver real-time visibility into application usage, network performance, and end-user experience.

## Purpose

ViewtiMon is deployed on Viewtinet's purpose-built appliances (or certified hardware with approved NICs). It provides the raw traffic intelligence that feeds the entire Viewtinet analytics stack — including [[viewtisight-overview|ViewtiSight]] for reporting and [[viewtiqos-overview|ViewtiQoS]] for traffic management.

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

ViewtiMon data feeds into [[viewtisight-overview|ViewtiSight]] for visualization, alarms, and long-term reporting. It is a prerequisite for [[viewtiqos-overview|ViewtiQoS]] deployment.

HA is not supported for ViewtiMon — only [[standalone-vs-cluster|standalone deployment]] is available. See [[viewtimon-installation]] for installation steps and fine-tuning details.

See [[installation-guide-hub|Installation Guide Hub]] for related source documentation.
