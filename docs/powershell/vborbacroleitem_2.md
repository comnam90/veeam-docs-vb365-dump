---
title: "VBORbacGroup"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborbacroleitem_2.html"
last_updated: "1/9/2026"
product_version: "8.3.0.2201"
---

# VBORbacGroup


Contains details about a group that is managed by restore operators or is excluded. See also [VBORbacRoleItem](vborbacroleitem.md).

| Property | Type | Description |
| --- | --- | --- |
| OfficeId | GUID | ID of the group in the Microsoft 365 organization. |
| OnPremisesId | GUID | ID of the group in the on-premises organization. |
| DisplayName | String | Group display name. |
| GroupName | String | Group name. |
| Type | VBORbacGroupType | Group type. Possible values:   * Office 365 * Security * Distribution * DynamicDistribution * Unknown |

Related Commands

* [New-VBORbacRoleItem](new-vborbacroleitem.md)
* [Add-VBORbacRole](add-vborbacrole.md)
* [Set-VBORbacRole](set-vborbacrole.md)


