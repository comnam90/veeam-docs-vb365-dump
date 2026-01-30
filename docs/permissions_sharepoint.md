---
title: "Microsoft SharePoint and OneDrive for Business"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_sharepoint.html"
last_updated: "7/5/2024"
product_version: "8.3.0.2201"
---

# Microsoft SharePoint and OneDrive for Business


The following tables list roles and permissions that must be assigned to Veeam Backup account to protect data in Microsoft SharePoint and OneDrive for Business organizations. Veeam Backup for Microsoft 365 requires these roles and permissions for Microsoft 365 organizations that use modern authentication method with legacy protocols allowed or basic authentication method, and on-premises Microsoft organizations.

Consider the following:

* To add Microsoft SharePoint Online organizations, make sure that the LegacyAuthProtocolsEnabled parameter is enabled.

To enable this parameter, use the following cmdlet:

|  |
| --- |
| Set-SPOTenant -LegacyAuthProtocolsEnabled:$true |

For more information about the Set-SPOTenant cmdlet, see [this Microsoft article](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps).

* The account you use to add an organization must be a member of this organization.

|  |
| --- |
| Note |
| For more information about permissions required to restore Microsoft SharePoint data from backups created by Veeam Backup for Microsoft 365, see [Permissions](https://helpcenter.veeam.com/docs/vbo365/explorers/vesp_permissions.html?ver=80) for Veeam Explorer for Microsoft SharePoint. |

On-Premises Microsoft SharePoint Organizations

The following table lists roles that must be assigned to the account that you want to use to add on-premises Microsoft SharePoint organizations:

| Role | Description |
| --- | --- |
| Site Collection Administrator | Required to back up Microsoft SharePoint sites.  The account must be a member of the Farm Administrator group. |

Microsoft SharePoint Online Organizations

The following table lists roles that must be assigned to the account that you want to use to add Microsoft SharePoint Online organizations:

| Role | Description |
| --- | --- |
| SharePoint Admin | Required to back up Microsoft SharePoint sites. |
| View-only Configuration | Required to get a list of available groups and users. |
| View-Only Recipients |

|  |
| --- |
| Tip |
| You can assign the Global Admin role that overrides these roles. |

Granting SharePoint Administrator Role in PowerShell

To grant the SharePoint Administrator role using PowerShell (for Microsoft SharePoint Online organizations), use the following example:

|  |
| --- |
| Connect-MsolService  $role=Get-MsolRole -RoleName "SharePoint Administrator"  $accountname="example@domain.com"  Add-MsolRoleMember -RoleMemberEmailAddress $accountname -RoleName $role.Name |

The $accountname variable must be a user UPN (example@domain.com).

The MSOL module can be downloaded from [this Microsoft page](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).


