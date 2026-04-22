---
title: "Upload License"
description: "After completing the three-step bundle installation and activating the admin user, you must upload the license file provided by your Viewtinet representative..."
keywords: "instalacion, licencias"
---

# Upload License

After completing the [three-step bundle installation](installation-bundle-steps.md) and activating the admin user, you must upload the license file provided by your Viewtinet representative to activate the platform features.

## Prerequisites

- The [bundle installation](installation-bundle-steps.md) must be complete
- [User Admin Activation](user-admin-activation.md) must have been performed — you need the admin password
- A `.key` license file received from your Viewtinet representative (obtained after submitting [Server Info](server-info.md))

## Procedure

1. Open a web browser and navigate to `http://<SERVER_IP>:4200`
2. Log in using the **admin** user and the password set during [User Admin Activation](user-admin-activation.md)
3. In the **App Selector** screen, choose **Viewtimanager**
4. Click the **LOAD LICENSE FILE** button
5. Select the `.key` file provided by Viewtinet
6. Confirm the upload

Once the file is uploaded, the features of [ViewtiManager](../productos/viewtimanager-overview.md) are activated and you can proceed with module installations.

## Cluster Licensing

Each node in a [cluster deployment](../conceptos/standalone-vs-cluster.md) requires its own license. For multi-node setups such as [ViewtiSight cluster](viewtisight-installation.md) or [ViewtiLog cluster](viewtilog-installation.md), you must:

1. Retrieve `server-info.txt` from each node via [Server Info](server-info.md)
2. Send each file to your Viewtinet representative
3. Receive and upload a separate `.key` file on each node

## Access URL

The Viewtimanager GUI is always accessible at port **4200** on the management IP address. In HA clusters, the floating VIP is used instead of individual node IPs.

See [Installation Guide Hub](../fuentes/installation-guide-hub.md) for the complete source index.
