---
tags: [instalacion, licencias]
tipo: tecnica
fuentes: ["documentation_hub"]
fecha_creacion: 2026-04-21
fecha_actualizacion: 2026-04-21
---

# Upload License

After completing the [[installation-bundle-steps|three-step bundle installation]] and activating the admin user, you must upload the license file provided by your Viewtinet representative to activate the platform features.

## Prerequisites

- The [[installation-bundle-steps|bundle installation]] must be complete
- [[user-admin-activation]] must have been performed — you need the admin password
- A `.key` license file received from your Viewtinet representative (obtained after submitting [[server-info]])

## Procedure

1. Open a web browser and navigate to `http://<SERVER_IP>:4200`
2. Log in using the **admin** user and the password set during [[user-admin-activation]]
3. In the **App Selector** screen, choose **Viewtimanager**
4. Click the **LOAD LICENSE FILE** button
5. Select the `.key` file provided by Viewtinet
6. Confirm the upload

Once the file is uploaded, the features of [[viewtimanager-overview|ViewtiManager]] are activated and you can proceed with module installations.

## Cluster Licensing

Each node in a [[standalone-vs-cluster|cluster deployment]] requires its own license. For multi-node setups such as [[viewtisight-installation|ViewtiSight cluster]] or [[viewtilog-installation|ViewtiLog cluster]], you must:

1. Retrieve `server-info.txt` from each node via [[server-info]]
2. Send each file to your Viewtinet representative
3. Receive and upload a separate `.key` file on each node

## Access URL

The Viewtimanager GUI is always accessible at port **4200** on the management IP address. In HA clusters, the floating VIP is used instead of individual node IPs.

See [[installation-guide-hub|Installation Guide Hub]] for the complete source index.
