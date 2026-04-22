---
title: "IPMI Management"
description: "The Intelligent Platform Management Interface (IPMI) provides out-of-band remote access to the Viewtinet appliance, independent of the operating system. It a..."
keywords: "conceptos, hardware, ipmi, gestion-remota"
---

# IPMI Management

The Intelligent Platform Management Interface (IPMI) provides out-of-band remote access to the [Viewtinet appliance](../productos/viewtinet-appliance.md), independent of the operating system. It allows administrators to monitor system health, manage boot processes, and control the server even when the OS is unresponsive.

## What IPMI Provides

- Remote access for multiple users from different locations
- System health monitoring (temperature, fans, power)
- Remote power control (power on/off/reset)
- Console redirection (keyboard and video over network)
- OS-independent management — functions even when the server is down

IPMI is essential before running the management IP change script (`change-management-ip.sh`) on the [Viewtinet Appliance](../productos/viewtinet-appliance.md), as it provides recovery access if the network configuration fails.

## Configuring the IPMI IP Address

IPMI IP configuration is performed via the BIOS Setup Utility at server boot — not through the OS.

### Procedure

1. Connect a keyboard and monitor to the appliance (see rear port layout in [Viewtinet Appliance](../productos/viewtinet-appliance.md))
2. Power on the appliance
3. When the SuperMicro message appears, press `DEL` to enter the Setup Utility
4. Use the right arrow key to navigate to the **IPMI** menu
5. Select **Update IPMI LAN Configuration** and press `Enter`
6. Choose **Yes** from the pop-up
7. Configure the following parameters using the down arrow key:
   - **Station IP Address**
   - **Subnet Mask**
   - **Gateway IP Address**
8. Press `F4` to save changes
9. Select **Yes** to confirm
10. The appliance reboots and IPMI becomes accessible via the web

Note: The IPMI port must be physically connected to the network for web-based access.

## Web-Based IPMI Access

Once configured, access the IPMI management interface from any browser:

```
https://<IPMI_IP>
```

Login credentials are provided by Viewtinet support (`support@viewtinet.com`) or your Viewtinet representative. The IPMI IP is distinct from the Viewtinet management IP — do not confuse the two.

## Remote Console

1. Log in to the IPMI web interface
2. Navigate to **Remote Control** in the left menu
3. Click **Launch Console** to open a virtual keyboard/video session to the server

Default CLI credentials for the console: user `viewtinet`, password `viewtinet`. Contact support if these credentials fail.

## Relationship to [Os Setup](../instalacion/os-setup.md) and Management IP

IPMI is separate from the OS management network. Always verify IPMI connectivity before changing the Viewtinet management IP via the `change-management-ip.sh` script. See [Viewtinet Appliance](../productos/viewtinet-appliance.md) for the full appliance setup context.

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the full source index.
