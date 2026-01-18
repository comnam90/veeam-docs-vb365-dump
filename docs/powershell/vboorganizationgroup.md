---
title: "VBOOrganizationGroup"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboorganizationgroup.html"
last_updated: "12/17/2025"
product_version: "8.3.0.2201"
---

# VBOOrganizationGroup


Contains details about an organization group.

| Property | Type | Description |
| --- | --- | --- |
| OrganizationId | GUID | Microsoft organization ID. |
| OfficeId | GUID | ID of the group in the Microsoft 365 organization. |
| OnPremisesId | GUID | ID of the group in the on-premises organization. |
| DisplayName | String | Display name of the organization group. |
| GroupName | String | Group name of the organization group. |
| Type | VBOOrganizationGroupType | Organization group type. Possible values:   * Office 365 * Security * Distribution * DynamicDistribution |
| LocationType | VBOLocationType | Microsoft 365 organization deployment type. Possible values:   * Office * OnPremises * Hybrid |

Related Commands

* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)
* [Get-VBOOrganizationGroupMember](get-vboorganizationgroupmember.md)
* [New-VBORbacOperator](new-vborbacoperator.md)
* [New-VBORbacRoleItem](new-vborbacroleitem.md)
* [Get-VBOEntityData](get-vboentitydata.md)


