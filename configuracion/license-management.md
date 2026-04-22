---
tags: [configuracion, viewtimanager, licencias]
tipo: tecnica
fuentes: ["viewtimanager-user-guide"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# License Management

Viewtinet's license enforcement system controls which modules and features remain active, and provides warnings or restrictions as license terms approach or exceed their limits. Licenses are managed from the **License** section of the [[gui-overview|ViewtiManager sidebar]].

For the initial license upload procedure, see [[upload-license]].

## License Enforcement Behavior

### Expiration

- When a temporal license **expires**, ViewtiMon, ViewtifyQoS, ViewtiLog, and other modules are disabled. You can still log in to [[viewtimanager-overview|ViewtiManager]] itself.
- [[viewtisight-overview|ViewtiSight]] becomes entirely inaccessible until a valid license is loaded.

### Expiry Warning

When a temporal license is within **30 days** of its expiration date, or a permanent license support period is within 30 days of ending, ViewtiManager displays a yellow popup warning. Functionality remains uninterrupted during this warning period.

### Module Enable/Disable

If a module is disabled in the license file, specific database tables are blocked:

| Module | Blocked Resources |
|---|---|
| [[viewtimon-overview|ViewtiMon]] | `dpi_records`, `voip_records` |
| ViewtifyQoS | `qos_records` |
| ViewtiMon Sniffer | `pcap_storage_records` |
| [[viewtilog-overview|ViewtiLog]] | All tables except DPI, VoIP, QoS, and self-monitoring |

## License Scenarios

| Scenario | Behavior |
|---|---|
| Compliant | All modules work normally; serial number shown at top of License section |
| Temporal expiry within 30 days | Yellow warning popup; functionality uninterrupted |
| Permanent support within 30 days | Similar warning displayed; modules keep working |
| Temporal license expired | All modules except ViewtiManager disabled; ViewtiSight inaccessible |
| Permanent support expired | Modules remain functional; expired message shown |
| Usage above warning limits | Non-blocking alert shown in License section |
| Usage above deny limits (not yet non-compliant) | Warning shown; events logged in License history |
| Non-compliant (deny exceeded 7+ days) | Module tables blocked; must wait 30 days or load expanded license |

## Limit Types

License limits track three dimensions:
- **GB/day** — data ingestion volume
- **Throughput** — network traffic throughput
- **Device count** — number of managed devices

Exceeding warning limits triggers alerts. Exceeding deny limits for seven consecutive days (or equivalent for throughput buckets) declares non-compliance and blocks the affected module until a new license is applied or 30 days pass.

## Related Pages

- [[upload-license]] — Initial license file upload procedure
- [[server-info]] — Server information required to obtain a license
- [[viewtimanager-overview]] — Platform overview including module list
- [[system-updates]] — Platform update procedure
