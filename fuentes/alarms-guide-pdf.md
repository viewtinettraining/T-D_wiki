---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Alarms User Guide PDF — Source Summary'
id: DGQ-ZYX-R2R-ZUE
slug: alarms-guide-pdf
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Alarms User Guide PDF — Source Summary

This page summarizes the Alarms User Guide (v6.3.5, r1.1), which covers the full alarm management lifecycle in [ViewtiSight](../productos/viewtisight-features.md) and the Viewtinet Control Center. It includes alarm filtering, acknowledgment, silencing, configuration, and notification setup.

## Alarm Panel Overview

The alarm panel in the Control Center displays active alarms with columns for: Alarm Name, Severity (Critical / Major / Minor / Clear), Time Check, Duration, Applied Rule, Data Source, Dimensions, Metric, and Comments. The [alarm system](../conceptos/alarms-system.md) integrates with the ETL process executed by [the Dhyana pipeline](../productos/vs-data-broker-overview.md).

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

1. **Real-time alarms** — evaluate metrics during each ETL cycle; created inside the [VSDB plugin](../conceptos/data-sources-integration.md) configuration
2. **Scheduled alarms** — evaluate [Metrics Composer](../productos/viewtisight-features.md) metrics at configured intervals (e.g., every 1 minute, hourly)

## Alarm Configuration

Creating a scheduled alarm requires: a provisioned data source with active datasets, and a metric created in Metrics Composer. Configuration steps include selecting a dataset, adding the metric to evaluate, defining [dimensions](../configuracion/roles.md), setting column filters, creating rules with thresholds, and configuring a scheduler. See [Alarms System](../conceptos/alarms-system.md) for full configuration details.

## Notifications

Supported notification channels:
- **Email** — requires SMTP server integration configured in [Viewtimanager Overview](../productos/viewtimanager-overview.md)
- **Telegram, Teams, WhatsApp** — require advanced configuration (contact support@viewtinet.com)
- **Scripts** — automated response execution

The Notifications Panel shows execution status for each triggered notification, allowing verification and troubleshooting.
