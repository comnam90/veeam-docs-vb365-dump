---
title: "VBOLicensedUser"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbolicenseduser.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOLicensedUser


Contains details about a licensed Veeam Backup for Microsoft 365 user.

| Property | Type | Description |
| --- | --- | --- |
| UserName | String | Name of the licensed Veeam Backup for Microsoft 365 user. |
| OfficeId | GUID | ID of the user in the Microsoft 365 organization. |
| OnPremisesId | GUID | ID of the user in the on-premises organization. |
| IsBackedUp | Bool | If True, the licensed Veeam Backup for Microsoft 365 user was processed by a backup job. |
| LastBackupDate | DateTime | Date and time when the user was processed by a backup job for the last time. |
| LicenseStatus | VBOLicenseStatus | Current status of the licensed user. Possible values:   * Licensed * New * TemporaryAssigned * Exceeded |
| OrganizationId | GUID? | Microsoft organization ID. |
| BackedUpOrganizationId | VBOOrganizationId | ID of the backed-up organization in the backup. |
| OrganizationName | String | Microsoft organization name. |

Related Commands

* [Get-VBOLicensedUser](get-vbolicenseduser.md)
* [Remove-VBOLicensedUser](remove-vbolicenseduser.md)


