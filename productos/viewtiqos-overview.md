---
title: "ViewtiQoS Overview"
description: "ViewtiQoS (also referred to as Viewtify QoS) extends Viewtinet's DPI capabilities into an enterprise-grade traffic management engine. It enables real-time cl..."
keywords: "productos, viewtiqos, qos, trafico"
---

# ViewtiQoS Overview

ViewtiQoS (also referred to as Viewtify QoS) extends Viewtinet's DPI capabilities into an enterprise-grade traffic management engine. It enables real-time classification, prioritization, and shaping of network flows to guarantee performance for mission-critical services.

## Purpose

ViewtiQoS is deployed on top of [ViewtiMon](viewtimon-overview.md) — which is a hard prerequisite. It translates ViewtiMon's traffic intelligence into active policy enforcement, allowing network operators to control how bandwidth is allocated per application, user group, or business service.

## Key Capabilities

- **Deep Packet Classification** — Leverages DPI to accurately identify applications, protocols, and metadata on every flow, including on non-standard ports or encrypted traffic
- **Bandwidth Allocation and Traffic Shaping** — Defines granular shaping rules to allocate fixed or dynamic bandwidth shares, preventing any single flow from starving critical services during peak load
- **Priority Queuing and Scheduling** — Assigns priority levels (real-time voice/video, mission-critical business apps, bulk transfers) and enforces strict or weighted-fair queuing to guarantee low latency and jitter
- **Real-Time Policy Enforcement** — Pushes policy changes instantly across probes and collectors, with live telemetry on bandwidth usage, queue depths, and dropped packets

## Deployment Constraints

- ViewtiQoS is **normally deployed on Viewtinet's purpose-built appliances**. Partners and distributors generally do not perform this installation unless there is an explicit commercial exception
- **HA is not supported** — only single-node deployment is available in the current release
- Requires exclusive NIC binding, which means [ViewtiMon](viewtimon-overview.md) must be stopped and restarted during NIC assignment — see [Viewtiqos Installation](../instalacion/viewtiqos-installation.md)

## Integration

ViewtiQoS sits alongside [ViewtiMon](viewtimon-overview.md) on the same host and is managed through [ViewtiManager](viewtimanager-overview.md). Traffic-shaping policies interact directly with the probe NICs that ViewtiMon uses for traffic capture.

For installation steps, see [Viewtiqos Installation](../instalacion/viewtiqos-installation.md). For deployment mode considerations, see [Standalone Vs Cluster](../conceptos/standalone-vs-cluster.md).

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for related source documentation.
