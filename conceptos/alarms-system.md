---
tags: [conceptos, alarmas, alertas, notificaciones, viewtisight]
tipo: tecnica
fuentes: ["alarms-user-guide_en_v6.3_1.0"]
fecha_creacion: 2026-04-22
fecha_actualizacion: 2026-04-22
---

# Alarms System

The Viewtinet alarms system provides real-time and scheduled alerting based on data processed by the [[etl-pipeline|ETL pipeline]] and metrics defined in [[viewtisight-features|ViewtiSight]]. Alarms notify operations teams of threshold violations and anomalous conditions, enabling rapid incident response.

## Alarm Types

### Real-Time Alarms

Real-time alarms are evaluated during each ETL cycle executed by the [[vs-data-broker-overview|VS Data Broker]] plugin. They are configured inside the plugin definition and fire as soon as a condition is detected in the incoming data stream. These alarms are suitable for high-frequency, low-latency alerting on raw telemetry.

### Scheduled Alarms

Scheduled alarms evaluate [[viewtisight-features|Metrics Composer]] outputs at configurable intervals (e.g., every 1 minute, hourly, or daily). They require:

1. A provisioned [[data-sources-integration|data source]] with active datasets
2. A metric defined in the Metrics Composer
3. A rule specifying threshold conditions and severity

Scheduled alarms are more flexible and support complex, multi-dimensional conditions.

## Severity Levels

| Severity | Color | Description |
|----------|-------|-------------|
| Critical | Red | Immediate action required; service impact likely |
| Major | Orange | Significant degradation; investigate promptly |
| Minor | Yellow | Potential issue; monitor and plan response |
| Clear | Green | Condition has returned to normal |

Severity is defined per rule during alarm configuration.

## Alarm Configuration

Creating a scheduled alarm involves these steps in the [[gui-overview|ViewtiSight Control Center]]:

1. Select a dataset (set) from an installed plugin
2. Add the metric to evaluate
3. Define dimension filters (e.g., filter by device or interface)
4. Create rules with thresholds and assign severity levels
5. Configure a scheduler (polling interval)
6. Attach a notification channel

Only [[roles|users with the appropriate role]] can create or modify alarm rules. Alarms are scoped per [[tenants|tenant]].

## Alarm Management Operations

The Control Center alarm panel supports the following actions:

| Action | Description |
|--------|-------------|
| Filter | Column-based filters (Contains, Equals, Starts With, etc.) with AND/OR logic |
| Mark as Read | Individual, multiple, or all alarms |
| Acknowledge | Multi-user acknowledgment; records the username |
| Silence | Suppress notifications for a configured duration |
| Hide | Remove from default view; recoverable via checkbox |
| Add Comment | Shared context visible to all users |
| Reset | Manually clear an alarm; re-triggers if condition persists |

## Events Log

The Events Log provides a centralized historical view of all alarm events, including alarm name, severity, timestamp, applied rule, dimensions, and metrics. It supports the same filtering and column customization as the active alarms panel.

## Notification Channels

| Channel | Requirements |
|---------|-------------|
| Email | SMTP server configured in [[viewtimanager-overview|ViewtiManager]] |
| Telegram | Advanced configuration — contact Viewtinet support |
| Microsoft Teams | Advanced configuration — contact Viewtinet support |
| WhatsApp | Advanced configuration — contact Viewtinet support |
| Scripts | Automated response execution on alarm trigger |

The Notifications Panel displays execution status for each triggered notification, enabling verification and troubleshooting.

## API Access

Active alarms and alarm history are also accessible via the [[rest-api|ViewtiSight REST API]] `/alarms/` endpoints, enabling integration with ITSM and SIEM platforms.
