---
tags: [productos, viewtiqos, qos, trafico]
tipo: concepto
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# ViewtiQoS Overview

ViewtiQoS (also referred to as Viewtify QoS) extends Viewtinet's DPI capabilities into an enterprise-grade traffic management engine. It enables real-time classification, prioritization, and shaping of network flows to guarantee performance for mission-critical services.

## Purpose

ViewtiQoS is deployed on top of [[viewtimon-overview|ViewtiMon]] — which is a hard prerequisite. It translates ViewtiMon's traffic intelligence into active policy enforcement, allowing network operators to control how bandwidth is allocated per application, user group, or business service.

## Key Capabilities

- **Deep Packet Classification** — Leverages DPI to accurately identify applications, protocols, and metadata on every flow, including on non-standard ports or encrypted traffic
- **Bandwidth Allocation and Traffic Shaping** — Defines granular shaping rules to allocate fixed or dynamic bandwidth shares, preventing any single flow from starving critical services during peak load
- **Priority Queuing and Scheduling** — Assigns priority levels (real-time voice/video, mission-critical business apps, bulk transfers) and enforces strict or weighted-fair queuing to guarantee low latency and jitter
- **Real-Time Policy Enforcement** — Pushes policy changes instantly across probes and collectors, with live telemetry on bandwidth usage, queue depths, and dropped packets

## Deployment Constraints

- ViewtiQoS is **normally deployed on Viewtinet's purpose-built appliances**. Partners and distributors generally do not perform this installation unless there is an explicit commercial exception
- **HA is not supported** — only single-node deployment is available in the current release
- Requires exclusive NIC binding, which means [[viewtimon-overview|ViewtiMon]] must be stopped and restarted during NIC assignment — see [[viewtiqos-installation]]

## Integration

ViewtiQoS sits alongside [[viewtimon-overview|ViewtiMon]] on the same host and is managed through [[viewtimanager-overview|ViewtiManager]]. Traffic-shaping policies interact directly with the probe NICs that ViewtiMon uses for traffic capture.

For installation steps, see [[viewtiqos-installation]]. For deployment mode considerations, see [[standalone-vs-cluster]].

See [[installation-guide-hub|Installation Guide Hub]] for related source documentation.
