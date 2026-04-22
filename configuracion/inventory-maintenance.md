---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Inventory Maintenance'
id: LO5-K4T-DBQ-2GG
slug: inventory-maintenance
isVisible: true
lastUpdated: '2026-04-22 08:56:02'
---

# Inventory Maintenance

Beyond provisioning devices and credentials, the [Inventory](inventory-management.md) feature offers maintenance capabilities to keep data clean, organized, and tailored to your needs. These functions are available in the **Overview / Devices** tab of the Inventory section.

## Toggling Visible Columns

The **Visible columns** picker controls which device attributes are shown in the Inventory table. These are existing fields — this is not the place to add new columns.

1. Click the dropdown arrow next to **Visible columns** above the devices table.
2. Check or uncheck boxes beside attributes (e.g., `device`, `mac`, `oid_group_names`, `sw_version`, `sys_object_id`, `system_name`).
3. Click **Save Changes** to persist the layout.

## Adding Custom Columns

Extend the Inventory schema with new custom columns to capture attributes beyond those provided by [CSV](csv-provisioning.md), [Autodiscovery](autodiscovery.md), or [manual provisioning](manual-provisioning.md):

1. Click **+ Add New Column** next to the column picker.
2. In the modal, enter a **Name** (e.g., `rack_label`).
3. Optionally, check **Copy values from another column** and select a source column.
4. Click **OK**. The new column appears in the table and the visible columns picker.
5. Populate values individually or click **Apply to all** for a bulk default.
6. Click **Save Changes**.

Custom columns are fully integrated — available for filtering, bulk editing, and CSV export.

## Merging Duplicate Rows

When multiple rows represent the same device:

1. Select the checkboxes next to each duplicate row.
2. Click **Merge Duplicated Rows** in the toolbar.
3. Confirm which values to retain for each column.
4. Click **Merge** to consolidate into a single record.

## Deleting Records

To remove obsolete entries:

1. Select one or more rows using their checkboxes.
2. Click **Delete Selected Rows** (trash icon).
3. Confirm deletion in the prompt.

## Exporting to CSV

1. Apply filters and adjust visible columns as needed.
2. Click **Export** in the upper-right corner of the devices table.
3. Download the generated CSV file.

## Finding Plugins for a Specific Device

To know which [plugins](../conceptos/plugin-architecture.md) are collecting data from a given device:

1. In **Overview → Devices**, find the target row.
2. Click the **"Show plugins using this device"** icon on that row.
3. You are taken to the **Plugins** tab, pre-filtered to show only plugins tied to that device.

## Finding Devices Associated with a Pipeline

To audit which devices a specific pipeline targets:

1. In the Inventory screen, click the **Plugins** tab.
2. Expand the desired plugin (e.g., **network monitoring**).
3. Click the **"Show devices assigned to this pipeline"** icon on the pipeline row.
4. A device picker shows only rows matching that pipeline's filter.

## Related Pages

- [Inventory Management](inventory-management.md) — Inventory overview
- [Autodiscovery](autodiscovery.md) — Auto-discovery and OID group assignment
- [Csv Provisioning](csv-provisioning.md) — CSV import and column mapping
- [Manual Provisioning](manual-provisioning.md) — Manual device entry
- [Configuration Manager](configuration-manager.md) — Uses inventory devices for configuration tasks
