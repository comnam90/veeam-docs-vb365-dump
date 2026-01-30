---
title: "Restore Portal Usage Scenarios"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_operation_scenarios.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---

# Restore Portal Usage Scenarios


Restore Portal offers users two scenarios for data restore:

* Self-service restore. In this scenario, users explore and restore their own data from backups created by Veeam Backup for Microsoft 365. After a user logs in to Restore Portal, only data that Veeam Backup for Microsoft 365 has backed up for this user account is available to explore and restore.
* Operator restore. In this scenario, the Veeam Backup for Microsoft 365 administrator specifies a user (or a group in which this user is included) as a restore operator.

Restore operators have permissions to explore and restore data from backups for specific organization object types: users, groups (group members only), sites, teams, or the entire Microsoft 365 organization. Permissions are assigned to restore operators when the Veeam Backup for Microsoft 365 administrator adds a restore operator role. For more information on how to add a restore operator role, see [Adding Restore Operator Role](ssp_adding_operator_roles.md).

After a restore operator logs in to Restore Portal, the product shows backed-up data for objects that the restore operator is allowed to manage — that is, to explore and restore data from backups created by Veeam Backup for Microsoft 365 for these objects.

Restore operators can work separately with data of the managed objects. Restore Portal allows them to switch between the managed objects. For more information on how to select an object whose backed-up data a restore operator will explore and restore, see [Changing Restore Operator Scope](ssp_changing_scope.md).

Restore operations that end users and restore operators can perform with the backed-up data are the same in both usage scenarios.


