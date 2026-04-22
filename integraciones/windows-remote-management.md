---
tags: [integracion, winrm, windows, vs-data-broker]
tipo: tecnica
fuentes: ["snazzydocs-vsdb"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Windows Remote Management (WinRM) Connector

The **Windows Remote Management (WinRM) Connector** enables agentless monitoring of Windows servers by leveraging Microsoft's native WinRM protocol. It collects performance metrics, system information, and event logs without requiring additional software on the target hosts. This connector is the recommended replacement for the deprecated [[wmi-extractor|WMI Connector]].

## Key Capabilities

- **Performance Metrics**: CPU utilization, memory, disk I/O, network statistics
- **System Information**: Uptime, running processes, installed hotfixes, system configuration
- **Event Logs**: Windows Security, Application, and System event logs (logon attempts, service changes, errors)
- **Agentless**: Communicates over HTTP/HTTPS with minimal overhead on monitored systems

## Prerequisites

Before configuring the WinRM Connector, the following steps must be completed on each target Windows server:

1. **Enable WinRM** via PowerShell: `winrm quickconfig` and enable basic authentication
2. **Create a dedicated WinRM user** and add them to the `Remote Management Users` group
3. **Configure HTTPS**: Generate or install a server authentication certificate and link it to WinRM
4. **Grant group memberships**: `Remote Management Users`, `Performance Log Users`, `Event Log Readers`
5. **Enable WMI permissions**: Grant `Remote Enable` and `Execute Methods` on the CIMV2 namespace
6. **Configure DCOM Access**: Grant `Remote Execution` and `Remote Activation` in Component Services
7. **Enable logon auditing**: Configure `secpol.msc` for logon event capture (Event IDs 4624, 4625)
8. **Firewall rule**: Open TCP port `5986` (WinRM HTTPS): `netsh advfirewall firewall add rule name="WinRM HTTPS" protocol=TCP dir=in localport=5986 action=allow`
9. **Export certificate**: Export to `.cer`, copy to the Viewtilog server; convert to `.pem` if needed using OpenSSL

## Important Notes

- Group names (e.g., `Remote Management Users`) may differ depending on the Windows OS language.
- Deleting or replacing the certificate will interrupt the connection — always keep backups of `.cer` and `.pem` files.

## Typical Use Cases

- Monitoring resource consumption on critical Windows servers
- Collecting logon and security events from domain controllers
- Tracking disk usage on application servers within the [[etl-pipeline|ETL pipeline]]

## Related Pages

- [[wmi-extractor]] — Deprecated predecessor; not functional on modern Windows
- [[ssh-extractor]] — Linux/Unix equivalent for agentless remote monitoring
- [[etl-pipeline]] — ETL pipeline context
- [[plugin-categories]] — WMI category in VSDB includes WinRM
- [[vs-data-broker-overview]] — VSDB product overview
