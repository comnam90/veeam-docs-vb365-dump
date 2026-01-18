---
title: "VBORbacUser"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborbacuser.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBORbacUser


Contains details about a user that is managed by restore operators or is excluded. See also [VBORbacRoleItem](vborbacroleitem.md).

| Property | Type | Description |
| --- | --- | --- |
| OfficeId | GUID | ID of the user in the Microsoft 365 organization. |
| OnPremisesId | GUID | ID of the user in the on-premises organization. |
| DisplayName | String | User display name. |
| UserName | String | User name. |
| Type | VBORbacUserType | User type. Possible values:   * User * SharedMailbox * PublicMailbox |

Related Commands

* [New-VBORbacRoleItem](new-vborbacroleitem.md)
* [Add-VBORbacRole](add-vborbacrole.md)
* [Set-VBORbacRole](set-vborbacrole.md)


