---
title: "WMI Extractor"
description: "The WMI (Windows Management Instrumentation) Connector was designed to extract performance metrics, logs, and configuration data directly from Windows server..."
keywords: "integracion, wmi, windows, vs-data-broker"
---

# WMI Extractor

The **WMI (Windows Management Instrumentation) Connector** was designed to extract performance metrics, logs, and configuration data directly from Windows servers through the WMI interface. It operates as a scheduled pipeline that runs periodic queries to collect CPU usage, memory, disk statistics, and other system counters.

## Important Limitation

Due to a **Microsoft security update released in March 2013**, the use of WMI for remote queries has been restricted. As a result, the WMI Connector **cannot be used with Windows servers that have this patch installed** — which includes virtually all modern Windows systems.

For environments with up-to-date Windows systems, this connector is not functional. The recommended alternative is the [Windows Remote Management (WinRM) Connector](windows-remote-management.md), which is supported and secure.

## Recommendation

- Verify if the Windows version predates the March 2013 patch (not recommended for production environments).
- Otherwise, configure the environment to use [WinRM over HTTPS](windows-remote-management.md), which provides equivalent capabilities without the security restriction.

## Context

The WMI Connector is listed in the [WMI category](../conceptos/plugin-categories.md) of the [VSDB](../productos/vs-data-broker-overview.md) GUI. While it appears as an available connector in the [Extract stage](../conceptos/etl-pipeline.md), its practical use is limited to legacy Windows environments. New deployments should use [WinRM](windows-remote-management.md) instead.

## Related Pages

- [Windows Remote Management](windows-remote-management.md) — Current recommended replacement for WMI
- [Ssh Extractor](ssh-extractor.md) — Linux/Unix equivalent for remote system metrics
- [Etl Pipeline](../conceptos/etl-pipeline.md) — Full ETL pipeline context
- [Plugin Categories](../conceptos/plugin-categories.md) — WMI is a dedicated category in VSDB
- [Vs Data Broker Overview](../productos/vs-data-broker-overview.md) — VSDB product overview
