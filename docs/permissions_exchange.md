---
title: "permissions_exchange"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_exchange.html"
last_updated: "7/8/2024"
product_version: "8.3.0.2201"
---


In this article

The following table lists roles and permissions that must be assigned to Veeam Backup account to protect data in Microsoft Exchange organizations. Veeam Backup for Microsoft 365 requires these roles and permissions for Microsoft 365 organizations that use modern authentication method with legacy protocols allowed or basic authentication method, and on-premises Microsoft organizations.

Consider the following:

* The account you use to add an organization must be a member of this organization.
* The account you use to add an organization is not required to have a mailbox in this organization.
* If you plan to back up public folder mailboxes, Veeam Backup account must have a valid Exchange Online license and an active mailbox within the Microsoft 365 organization.

|  |
| --- |
| Note |
| For more information about permissions required to restore Microsoft Exchange data from backups created by Veeam Backup for Microsoft 365, see [Permissions](https://helpcenter.veeam.com/docs/vbo365/explorers/vex_required_permissions.html?ver=80) for Veeam Explorer for Microsoft Exchange. |

| Role | Description |
| --- | --- |
| Role Management | Required to grant the ApplicationImpersonation role. |
| ApplicationImpersonation | Required to back up Exchange data. |
| Organization Configuration | Required to manage role assignments. |
| View-Only Configuration | Required to obtain necessary configuration parameters. |
| View-Only Recipients | Required to view mailbox recipients. |
| Mailbox Search or Mail Recipients | Required to back up groups. |
| Owner | Required to back up and restore public folders. |

Granting ApplicationImpersonation Role in PowerShell

For On-Premises Microsoft Exchange Organizations

To grant the ApplicationImpersonation role for on-premises Microsoft Exchange organizations, do the following:

1. Connect to the Exchange server. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps).

1. Run the following cmdlet to grant the role:

|  |
| --- |
| New-ManagementRoleAssignment –Role ApplicationImpersonation –User "Administrator" |

For Microsoft 365 Exchange Organizations

To grant the ApplicationImpersonation role for Microsoft 365 Exchange organizations, do the following:

1. Connect to the Exchange server:

* For Basic Authentication, see [this Microsoft article](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
* For Modern Authentication, see [this Microsoft article](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps).

1. Run the following cmdlet to grant the role:

|  |
| --- |
| New-ManagementRoleAssignment –Role ApplicationImpersonation –User user.name@domain.com |

Checking and Removing ApplicationImpersonation Role in PowerShell

To obtain the list of users whom the ApplicationImpersonation role has already been granted, use the following cmdlet (for both on-premises and Online organizations):

|  |
| --- |
| Get-ManagementRoleAssignment -Role "ApplicationImpersonation" |

To remove the role, use the following cmdlet (for both on-premises and Online organizations):

|  |
| --- |
| Get-ManagementRoleAssignment -RoleAssignee "Administrator" -Role ApplicationImpersonation -RoleAssigneeType user | Remove-ManagementRoleAssignment |

Creating and Configuring New Authentication Policy for Exchange Online Organizations

For Microsoft 365 Exchange organizations that use either modern authentication method with legacy protocols allowed or basic authentication method, you need to create a new authentication policy to protect Exchange Online data. This policy must have the AllowBasicAuthPowershell and AllowBasicAuthWebService parameters enabled for Veeam Backup account. To do this, use the following example:

|  |
| --- |
| New-AuthenticationPolicy -Name "Allow Basic Auth"  Set-AuthenticationPolicy -Identity "Allow Basic Auth" -AllowBasicAuthPowershell  Set-AuthenticationPolicy -Identity "Allow Basic Auth" -AllowBasicAuthWebService  Set-User -Identity <VeeamBackupAccount> -AuthenticationPolicy "Allow Basic Auth" |

To back up public folder mailboxes correctly, enable the AllowBasicAuthAutodiscover parameter for the created authentication policy using the following cmdlet:

|  |
| --- |
| Set-AuthenticationPolicy -Identity "Allow Basic Auth" -AllowBasicAuthAutodiscover |

Page updated 7/8/2024

Page content applies to build 8.3.0.2201
