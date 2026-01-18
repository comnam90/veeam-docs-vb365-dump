---
title: "VBOOperatorRole"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbooperatorrole.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOOperatorRole


Contains details about a restore operator role.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Restore operator role ID. |
| OrganizationId | GUID | Microsoft organization ID. |
| Name | String | Name of the restore operator role. |
| Description | String | Restore operator role description. |
| RoleType | VBOOperatorRoleType | Restore operator role type. Possible values:   * EntireOrganization * SpecificObjects |
| Operators | [VBORbacOperator](vborbacoperator.md)[] | Array of restore operators. |
| SelectedItems | [VBORbacRoleItem](vborbacroleitem.md)[] | Array of objects to manage. |
| ExcludedItems | [VBORbacRoleItem](vborbacroleitem.md)[] | Array of excluded objects. |

Related Commands

* [Add-VBORbacRole](add-vborbacrole.md)
* [Get-VBORbacRole](get-vborbacrole.md)
* [Set-VBORbacRole](set-vborbacrole.md)

* [Remove-VBORbacRole](remove-vborbacrole.md)


