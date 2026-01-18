---
title: "VBOOrganizationUser"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboorganizationuser.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOOrganizationUser


Contains details about an organization user.

| Property | Type | Description |
| --- | --- | --- |
| OrganizationId | GUID | Microsoft organization ID. |
| OfficeId | GUID | ID of the user in the Microsoft 365 organization. |
| OnPremisesId | GUID | ID of the user in the on-premises organization. |
| DisplayName | String | Display name of the organization user. |
| UserName | String | Name of the organization user. |
| Office | String | Office location in the place of business of the organization user. |
| Type | VBOOrganizationUserType | Type of the organization user. Possible values:   * SharedMailbox * PublicMailbox * User |
| LocationType | VBOLocationType | Microsoft 365 organization deployment type. Possible values:   * Office * OnPremises * Hybrid |
| AssignedLicenses | [VBOOfficeLicense](vboofficelicense.md)[] | Array of licenses assigned to the organization user. |

Related Commands

* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBORbacOperator](new-vborbacoperator.md)
* [New-VBORbacRoleItem](new-vborbacroleitem.md)
* [Get-VBOEntityData](get-vboentitydata.md)


