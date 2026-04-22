---
tags: [fuentes, alarmas, viewtisight]
tipo: fuente
fuentes: ["alarms-user-guide_en_v6.3.5_r1.1"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Alarms User Guide PDF — Source Summary

This page summarizes the Alarms User Guide (v6.3.5, r1.1), which covers the full alarm management lifecycle in [[viewtisight-features|ViewtiSight]] and the Viewtinet Control Center. It includes alarm filtering, acknowledgment, silencing, configuration, and notification setup.

## Alarm Panel Overview

The alarm panel in the Control Center displays active alarms with columns for: Alarm Name, Severity (Critical / Major / Minor / Clear), Time Check, Duration, Applied Rule, Data Source, Dimensions, Metric, and Comments. The [[alarms-system|alarm system]] integrates with the ETL process executed by [[vs-data-broker-overview|the Dhyana pipeline]].

## Alarm Management Operations

- **Filter** — column-based filters using Contains, Equals, Starts With, Ends With, Not Contains, Not Equals with AND/OR logic
- **Mark as Read** — individual, multiple, or all alarms
- **Acknowledge** — multi-user acknowledgment; displays the username who acknowledged
- **Silence** — suppress notifications for a configured duration; alarm remains visible
- **Hide** — remove from default view; recoverable via "Show hidden Alarms" checkbox
- **Add Comment** — shared context visible to all users
- **Reset** — manually clear an alarm; re-triggers if the condition persists

## Events Log

The Events Log provides a centralized historical view of all alarm events, including alarm name, severity, timestamp, applied rule, dimensions, and metrics. Filtering and column customization work identically to the active alarms panel.

## Alarm Types

Two alarm types are described in this guide:

1. **Real-time alarms** — evaluate metrics during each ETL cycle; created inside the [[data-sources-integration|VSDB plugin]] configuration
2. **Scheduled alarms** — evaluate [[viewtisight-features|Metrics Composer]] metrics at configured intervals (e.g., every 1 minute, hourly)

## Alarm Configuration

Creating a scheduled alarm requires: a provisioned data source with active datasets, and a metric created in Metrics Composer. Configuration steps include selecting a dataset, adding the metric to evaluate, defining [[roles|dimensions]], setting column filters, creating rules with thresholds, and configuring a scheduler. See [[alarms-system]] for full configuration details.

## Notifications

Supported notification channels:
- **Email** — requires SMTP server integration configured in [[viewtimanager-overview]]
- **Telegram, Teams, WhatsApp** — require advanced configuration (contact support@viewtinet.com)
- **Scripts** — automated response execution

The Notifications Panel shows execution status for each triggered notification, allowing verification and troubleshooting.
