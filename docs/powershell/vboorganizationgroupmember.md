---
title: "VBOOrganizationGroupMember"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboorganizationgroupmember.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBOOrganizationGroupMember


Contains details about an organization group member.

| Property | Type | Description |
| --- | --- | --- |
| OrganizationId | GUID | Microsoft organization ID. |
| Group | [VBOOrganizationGroup](vboorganizationgroup.md) | Details information about an organization group. |
| DisplayName | String | Display name of the organization group member. |
| Login | String | Login name. |
| Type | VBOOrganizationGroupMemberType | Type of the organization group member. Possible values:   * User * Group |

Related Commands

* [New-VBOBackupAccount](new-vbobackupaccount.md)
* [Get-VBOOrganizationGroupMember](get-vboorganizationgroupmember.md)


