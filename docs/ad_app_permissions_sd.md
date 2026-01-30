---
title: "Permissions for Modern App-Only Authentication"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ad_app_permissions_sd.html"
last_updated: "12/23/2025"
product_version: "8.3.0.2201"
---

# Permissions for Modern App-Only Authentication


Tables in this section list permissions for Microsoft Entra applications that are granted automatically by Veeam Backup for Microsoft 365 when you add organizations using the [modern app-only authentication method](adding_o365_organizations_sd.md).

If you prefer to use a custom application of your own, make sure to grant all the permissions listed in these tables manually to perform the following operations:

* [Backup](#backup)
* [Restore Using Device Code Flow](#codeflow)
* [Restore Using Application Certificate](#appcert)

|  |
| --- |
| Note |
| For a user account that the Microsoft Entra application will use to log in to Microsoft 365, consider the following:   * You must assign the [required roles](#accroles) to this user account. * If you plan to back up public folder mailboxes, this user account must have a valid Exchange Online license and an active mailbox within the Microsoft 365 organization. |

The following sections contain additional instructions that help you to check Office 365 Exchange Online API permissions and configure the Microsoft Entra application settings:

* [Checking Permissions for Office 365 Exchange Online API](permissions_exchange_online_api_checking.md)

Follow this instruction to check Office 365 Exchange Online API permissions in Microsoft Entra ID.

* [Configuring Microsoft Entra Application Settings](ad_application_settings_configuring.md)

Follow this instruction to configure the Microsoft Entra application settings in Microsoft Entra ID for data restore.

Veeam Backup for Microsoft 365 also requires you to grant permissions to Microsoft Entra applications that you add as backup applications. For more information, see [Backup Application Permissions](backup_app_permissions.md).

Required User Account Roles for Microsoft Entra Applications

Microsoft Entra application uses a user account to log in to Microsoft 365. This user account must be assigned the following roles:

* Global Administrator — required for adding organizations with modern app-only authentication, creating backup applications, registering Microsoft Entra application for Restore Portal and creating Microsoft Entra application for the Microsoft Azure service account.
* ApplicationImpersonation1, and Global Administrator or Exchange Administrator — required for data restore with Veeam Explorer for Microsoft Exchange.
* Global Administrator or SharePoint Administrator — required for data restore with Veeam Explorer for Microsoft SharePoint and Veeam Explorer for Microsoft OneDrive for Business.
* Global Administrator or Teams Administrator — required for data restore with Veeam Explorer for Microsoft Teams.
* Global Administrator — required for establishing a connection to a service provider in the [Backup as Service with Veeam Backup for Microsoft 365](vbo_mail_baas.md) scenario.
* Owner — requires to back up public folder mailboxes in organizations with modern app-only authentication.

1This role is not required for data restore using Microsoft Entra application certificate. It is recommended that you use modern authentication with the Microsoft Entra application certificate to restore Microsoft Exchange data. For more information, see [Restore Using Application Certificate](#appcert).

Granting Owner Role in PowerShell

To grant the Owner role to a user account that the Microsoft Entra application uses to log in to Microsoft 365, do the following:

1. Connect to the Exchange server. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps).
2. Use the following example to grant the role:

|  |
| --- |
| $folders = get-publicfolder "\" -recurse  foreach($folder in $folders)  {  Add-PublicFolderClientPermission -Identity $folder.identity -user <user\_account> -AccessRights Owner  } |

Permissions for Backup

All listed permissions are of the Application type.

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| --- | --- | --- | --- | --- | --- |
| Microsoft Graph | Directory.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for organization properties, the list of users and groups and their properties. |
| Group.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for the list of groups and group sites. |
| Sites.Read.All |  | ✔ | ✔ | Querying Microsoft Entra ID for the list of sites and getting download URLs for files and their versions. |
| TeamSettings.ReadWrite.All |  |  | ✔ | Accessing archived teams. |
| ChannelMessage.Read.All |  |  | ✔ | Accessing Microsoft Teams public channel messages. |
| ChannelMember.Read.All |  |  | ✔ | Accessing Microsoft Teams private and shared channels. |
| Office 365 Exchange Online1 | full\_access\_as\_app | ✔ |  | ✔ | Reading mailboxes content. |
| Exchange.ManageAsApp | ✔ |  |  | Accessing Exchange Online PowerShell to do the following:   * Back up public folder and discovery search mailboxes. * Determine object type for shared mailboxes as Shared Mailbox.   Note: This permission is required to back up public folder and discovery search mailboxes as well as determine correctly object type for shared mailboxes. This permission works along with the Global Reader role granted to the Microsoft Entra application. For more information, see [Granting Global Reader Role to Microsoft Entra Application](#app_role). |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ | ✔ | Reading SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ | ✔ | Reading OneDrive accounts (getting site IDs).  Note: This permission is not used to back up Microsoft Teams data, but you must grant it along with SharePoint Online and OneDrive for Business permission to add a Microsoft 365 organization successfully. |

1You can check permissions for Office 365 Exchange Online API. For more information, see [Checking Permissions for Office 365 Exchange Online API](permissions_exchange_online_api_checking.md).

Granting Global Reader Role to Microsoft Entra Application

Veeam Backup for Microsoft 365 supports backup of public folder and discovery search mailboxes and determines correctly object type for shared mailboxes in Microsoft 365 organizations with modern app-only authentication. To back up these objects, Veeam Backup for Microsoft 365 needs access to Exchange Online PowerShell. To do this, a Microsoft Entra application requires the Global Reader role. You must grant this role to the Microsoft Entra application after upgrading Veeam Backup for Microsoft 365 to version 8.

To grant the Global Reader role to the Microsoft Entra application, do the following:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).
2. Go to Identity > Roles & admins > Roles & admins.
3. In the Administrative roles list, find the Global Reader role and click on it.
4. In the Global Reader window, click Add assignments.

The Add assignments wizard runs.

1. In the Select member(s) section, click the link.
2. In the Select a member window, select the Microsoft Entra application in the list and click Select.

The selected application appears in the Selected member(s) list.

1. Click Next and then Assign to finish the wizard.

Permissions for Restore

|  |
| --- |
| Note |
| To restore data using Microsoft Entra application, make sure that you configure the Microsoft Entra application settings. For more information, see [Configuring Microsoft Entra Application Settings](ad_application_settings_configuring.md). |

Restore Using Device Code Flow

All listed permissions are of the Delegated type and required for data restore using Veeam Explorers.

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| --- | --- | --- | --- | --- | --- |
| Microsoft Graph | Directory.Read.All | ✔ | ✔ | ✔ | Querying Microsoft Entra ID for organization properties, the list of users and groups and their properties. |
| Group.ReadWrite.All |  |  | ✔ | Recreating in Microsoft Entra ID an associated group in case of teams restore. |
| Sites.Read.All |  | ✔ | ✔ | Accessing sites of the applications that are installed from the SharePoint store. |
| Directory.ReadWrite.All |  | ✔ | ✔ | When creating or accessing a M365 group for a Multi-Geo tenant in case of teams or sites restore:   * Setting the preferred data location.  * Creating sites that have Microsoft Teams templates. |
| offline\_access | ✔ | ✔ | ✔ | Obtaining a refresh token from Microsoft Entra ID. |
| ChannelMember.ReadWrite.All |  |  | ✔ | Reading the current state and restoring Microsoft Teams private and shared channels. |
| Office 365 Exchange Online1 | EWS.AccessAsUser.All | ✔ |  |  | Accessing mailboxes as the signed-in user (impersonation) through EWS. |
| full\_access\_as\_user | ✔ |  |  | Reading the current state and restoring mailboxes content.  Note: This permission is only required for organizations located in legacy Microsoft Entra Germany region. Veeam Backup for Microsoft 365 drops support for Microsoft 365 organizations in Microsoft Entra Germany region. To add organizations located in this region to Veeam Backup for Microsoft 365, run the [Add-VBOOrganization](https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboorganization.html?ver=80) cmdlet or use the POST /Organizations method. |
| Office 365 SharePoint Online | AllSites.FullControl |  | ✔ | ✔ | Reading the current state and restoring SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ |  | Resolving OneDrive accounts (getting site IDs).  Note: This permission is not required to restore SharePoint Online data. |

1You can check permissions for Office 365 Exchange Online API. For more information, see [Checking Permissions for Office 365 Exchange Online API](permissions_exchange_online_api_checking.md).

Restore Using Application Certificate

All listed permissions are of the Application type and required for the following scenarios of data restore:

* Data restore by Veeam Explorer for Microsoft Exchange using modern authentication with the Microsoft Entra application certificate. For more information, see the [Restore to Microsoft 365 Organizations](https://helpcenter.veeam.com/docs/vbo365/explorers/restore_to_o365.html?ver=80) section of the Veeam Explorers User Guide.
* Data restore using Restore Portal.
* Data restore through REST API and PowerShell.

| API | Permission name | Exchange Online | SharePoint Online and OneDrive for Business | Microsoft Teams | Description |
| --- | --- | --- | --- | --- | --- |
| Microsoft Graph | Directory.Read.All | ✔ |  | ✔ | Querying Microsoft Entra ID for organization properties, the list of users and groups and their properties. |
| Group.ReadWrite.All |  | ✔ | ✔ | Recreating in Microsoft Entra ID an associated group in case of a deleted team site restore.  Note: This permission is only required for restore of SharePoint site data through REST API and PowerShell. |
| Sites.Read.All |  | ✔ | ✔ | Accessing sites of the applications that are installed from the SharePoint store. |
| Directory.ReadWrite.All |  | ✔ | ✔ | When creating or accessing a M365 group for a Multi-Geo tenant in case of teams or sites restore:   * Setting the preferred data location.  * Creating sites that have Microsoft Teams templates. |
| Files.ReadWrite.All |  |  | ✔ | Reading the current state and restoring files of Microsoft Teams shared channels. |
| ChannelMember.ReadWrite.All |  |  | ✔ | Reading the current state and restoring Microsoft Teams private and shared channels. |
| Office 365 Exchange Online1 | full\_access\_as\_app | ✔ |  |  | Reading the current state and restoring mailboxes content. |
| Office 365 SharePoint Online | Sites.FullControl.All |  | ✔ | ✔ | Reading the current state and restoring SharePoint sites and OneDrive accounts content. |
| User.Read.All |  | ✔ |  | Resolving OneDrive accounts (getting site IDs).  Note: This permission is not required to restore SharePoint Online data. |

1You can check permissions for Office 365 Exchange Online API. For more information, see [Checking Permissions for Office 365 Exchange Online API](permissions_exchange_online_api_checking.md).


