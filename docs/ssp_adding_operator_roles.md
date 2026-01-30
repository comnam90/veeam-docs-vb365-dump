---
title: "Adding Restore Operator Role"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_adding_operator_roles.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---

# Adding Restore Operator Role


In the operator restore scenario, Veeam Backup for Microsoft 365 administrators must add restore operator roles.

When adding a restore operator role, they select organization users or groups and assign permissions to them. Such users or groups become restore operators. Restore operators are allowed to explore and restore data from backups created by Veeam Backup for Microsoft 365 for specific organization object types: users, groups (group members only), sites, teams, or the entire Microsoft 365 organization.

To add a restore operator role, [check prerequisites](before_you_begin_ssp.md) and do the following:

1. [Launch the New Restore Operator Role wizard](ssp_new_operator_role.md).
2. [Specify a role name](ssp_role_name.md).
3. [Select Microsoft organization](ssp_role_organization.md).
4. [Select restore operators](ssp_role_operators.md).
5. [Select objects to manage](ssp_role_objects_to_manage.md).
6. [Select objects to exclude](ssp_role_objects_to_exclude.md).


