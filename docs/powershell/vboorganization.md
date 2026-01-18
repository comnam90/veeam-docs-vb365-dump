---
title: "VBOOrganization"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboorganization.html"
last_updated: "1/15/2026"
product_version: "8.3.0.2201"
---

# VBOOrganization


Contains details about a Microsoft organization.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Microsoft organization ID. |
| Name | String | Microsoft organization name. |
| Description | String | Microsoft organization description. |
| IsBackedUp | Bool | If True, the organization was backed up. |
| LicensingOptions | [VBOLicensingOptions](vbolicensingoptions.md) | Licensing details. |
| Type | VBOOrganizationType | Microsoft organization type. Possible values:   * Office365 * OnPremises * Hybrid |
| Office365ExchangeConnectionSettings | [VBOOffice365ConnectionSettings](vbooffice365connectionsettings.md) | Connection settings for Microsoft Exchange Online. |
| Office365SharePointConnectionSettings | [VBOOffice365ConnectionSettings](vbooffice365connectionsettings.md) | Connection settings for Microsoft SharePoint Online and Microsoft OneDrive for Business. |
| OnPremExchangeConnectionSettings | [VBOExchangeOnPremConnectionSettings](vboexchangeonpremconnectionsettings.md) | Connection settings for Microsoft on-premises Exchange organization. |
| OnPremSharePointConnectionSettings | [VBOSharePointOnPremConnectionSettings](vbosharepointonpremconnectionsettings.md) | Connection settings for Microsoft on-premises SharePoint organization. |
| VeeamAADApplicationUsed | Bool | If True, the Veeam application is used to connect to Microsoft Graph. |
| BackupAccounts | [VBOBackupAccount](vbobackupaccount.md)[] | Array of auxiliary backup accounts. |
| BackupApplications | [VBOBackupApplication](vbobackupapplication.md)[] | Array of backup applications. |
| BackupParts | OrganizationBackupParts | Services that Veeam Backup for Microsoft 365 protects. Possible values:   * Office365Exchange * OnPremisesExchange * Office365SharePoint * OnPremisesSharePoint * Office365Teams * Office365TeamsChats * Office365All * OnPremisesAll |
| BackupTeams | Bool | If True, backup of Microsoft Teams is enabled. |
| BackupTeamsChats | Bool | If True, backup of team chats is enabled. |

Related Commands

* [Get-VBOLicensedUser](get-vbolicenseduser.md)
* [Get-VBOProxy](get-vboproxy.md)
* [Add-VBOOrganization](add-vboorganization.md)
* [Get-VBOOrganization](get-vboorganization.md)
* [Set-VBOOrganization](set-vboorganization.md)
* [Remove-VBOOrganization](remove-vboorganization.md)
* [Get-VBOOrganizationSynchronizationState](get-vboorganizationsynchronizationstate.md)
* [Start-VBOOrganizationSynchronization](start-vboorganizationsynchronization.md)
* [Get-VBOApplication](get-vboapplication.md)
* [New-VBOBackupApplication](new-vbobackupapplication.md)
* [Add-VBOBackupApplication](add-vbobackupapplication.md)
* [Get-VBOBackupApplication](get-vbobackupapplication.md)
* [Remove-VBOBackupApplication](remove-vbobackupapplication.md)
* [New-VBOBackupItem](new-vbobackupitem.md)
* [Add-VBOOrganizationRetentionExclusion](add-vboorganizationretentionexclusion.md)
* [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md)
* [Get-VBOOrganizationGroup](get-vboorganizationgroup.md)
* [Get-VBOOrganizationSite](get-vboorganizationsite.md)
* [Get-VBOOrganizationTeam](get-vboorganizationteam.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [Add-VBOJob](add-vbojob.md)
* [Get-VBOJob](get-vbojob.md)
* [Get-VBOMailboxProtectionReport](get-vbomailboxprotectionreport.md)
* [Get-VBOUserProtectionReport](get-vbouserprotectionreport.md)
* [Add-VBORbacRole](add-vborbacrole.md)
* [Get-VBORbacRole](get-vborbacrole.md)
* [Get-VBORestorePoint](get-vborestorepoint.md)
* [Get-VBOEntityData](get-vboentitydata.md)
* [Get-VBOUsageData](get-vbousagedata.md)
* [Get-VBODataRetrieval](get-vbodataretrieval.md)


