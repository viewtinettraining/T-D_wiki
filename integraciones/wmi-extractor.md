---
tags: [integracion, wmi, windows, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# WMI Extractor

The **WMI (Windows Management Instrumentation) Connector** was designed to extract performance metrics, logs, and configuration data directly from Windows servers through the WMI interface. It operates as a scheduled pipeline that runs periodic queries to collect CPU usage, memory, disk statistics, and other system counters.

## Important Limitation

Due to a **Microsoft security update released in March 2013**, the use of WMI for remote queries has been restricted. As a result, the WMI Connector **cannot be used with Windows servers that have this patch installed** — which includes virtually all modern Windows systems.

For environments with up-to-date Windows systems, this connector is not functional. The recommended alternative is the [[windows-remote-management|Windows Remote Management (WinRM) Connector]], which is supported and secure.

## Recommendation

- Verify if the Windows version predates the March 2013 patch (not recommended for production environments).
- Otherwise, configure the environment to use [[windows-remote-management|WinRM over HTTPS]], which provides equivalent capabilities without the security restriction.

## Context

The WMI Connector is listed in the [[plugin-categories|WMI category]] of the [[vs-data-broker-overview|VSDB]] GUI. While it appears as an available connector in the [[etl-pipeline|Extract stage]], its practical use is limited to legacy Windows environments. New deployments should use [[windows-remote-management|WinRM]] instead.

## Related Pages

- [[windows-remote-management]] — Current recommended replacement for WMI
- [[ssh-extractor]] — Linux/Unix equivalent for remote system metrics
- [[etl-pipeline]] — Full ETL pipeline context
- [[plugin-categories]] — WMI is a dedicated category in VSDB
- [[vs-data-broker-overview]] — VSDB product overview
