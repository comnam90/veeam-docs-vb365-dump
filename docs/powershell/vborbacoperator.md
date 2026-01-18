---
title: "VBORbacOperator"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborbacoperator.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBORbacOperator


Contains details about a user or a group that acts as restore operator.

| Property | Type | Description |
| --- | --- | --- |
| OrganizationId | GUID | Microsoft organization ID. |
| OfficeId | GUID | ID of the user or group in the Microsoft 365 organization. |
| OnPremisesId | GUID | ID of the user or group in the on-premises organization. |
| DisplayName | String | Display name of the user or group. |
| UserName | String | User name. |
| GroupName | String | Group name. |
| Type | VBORbacUserType | User type. Possible values:   * User * SharedMailbox * PublicMailbox |
| Type | VBORbacGroupType | Group type. Possible values:   * Office 365 * Security * Distribution * DynamicDistribution * Unknown |

Related Commands

* [New-VBORbacOperator](new-vborbacoperator.md)
* [Add-VBORbacRole](add-vborbacrole.md)
* [Set-VBORbacRole](set-vborbacrole.md)


