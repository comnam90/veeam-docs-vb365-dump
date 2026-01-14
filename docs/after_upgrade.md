---
title: "after_upgrade"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/after_upgrade.html"
last_updated: "8/13/2025"
product_version: "8.3.0.2201"
---


In this article

After you upgraded Veeam Backup for Microsoft 365 to version 8, it is recommended to do the following:

* For Microsoft 365 organizations that you may have in the Veeam Backup for Microsoft 365 console from previous installations of the product:

* Switch organizations that use basic authentication and modern authentication with legacy protocols allowed to modern app-only authentication.
* Configure backup of public folder and discovery search mailboxes for organizations with modern app-only authentication.
* Configure backup and restore of Microsoft Teams private and shared channels for organizations with modern app-only authentication.

* Upgrade the Veeam Backup for Microsoft 365 REST API component on a separate machine.
* Upgrade backup proxy servers and backup repositories.
* Manually remove a directory that stores object storage cache created in previous installations of Veeam Backup for Microsoft 365.

Switching Organizations to Modern App-Only Authentication

You can continue to use Veeam Backup for Microsoft 365 version 8 to back up and restore data of Microsoft 365 organizations that were added to previous installations of the product using basic authentication or modern authentication with legacy protocols allowed. Since Microsoft deprecated basic authentication and legacy authentication protocols, it is recommended to change the authentication method to modern app-only authentication for such organizations. For more information, see [this Microsoft article](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437).

|  |
| --- |
| Note |
| This action is optional and cannot be reverted. |

To change authentication method, do the following:

1. Edit your Microsoft 365 organization that uses legacy authentication methods. For more information, see [Editing Organization Settings](vbo_editing_org.md).
2. Select the Modern authentication option to use Microsoft Entra application to connect to your Microsoft 365 organization. For more information, see [Select Microsoft Entra Region and Authentication Method](vbo_add_o365_2_sd.md).

Configuring Backup of Public Folder and Discovery Search Mailboxes

You can allow Veeam Backup for Microsoft 365 to back up public folder and discovery search mailboxes and determine correctly object type for shared mailboxes in Microsoft 365 organizations with modern app-only authentication that were added to previous installations of the product. This functionality requires a Microsoft Entra application to be granted the Exchange.ManageAsApp permission and the Global Reader role.

To update permissions of the Microsoft Entra application, do the following:

1. Edit your Microsoft 365 organization with modern app-only authentication. For more information, see [Editing Organization Settings](vbo_editing_org.md).
2. Select the Use an existing Microsoft Entra ID application option to connect to your Microsoft 365 organization.
3. Click Install to run the Select Certificate wizard.
4. Proceed to any of the following options:

* [Select certificate from the Certificate Store of this server](vbo_installing_certificate.md#selecting_file)
* [Import certificate from a PFX file](vbo_installing_certificate.md#import)

1. Select the Grant the required permissions to this application and register its certificate in Microsoft Entra ID check box to automatically update permissions of the existing Microsoft Entra application. For more information, see [Using Existing Microsoft Entra Application](register_ad_application.md#uea).

Alternatively, you can sign in to Microsoft Identity platform and manually grant this Microsoft Entra application the Exchange.ManageAsApp permission and the Global Reader role. For more information, see [Permissions for Backup](ad_app_permissions_sd.md#Exchange.ManageAsApp) and [Granting Global Reader Role to Microsoft Entra Application](ad_app_permissions_sd.md#app_role).

Configuring Backup and Restore of Microsoft Teams Private and Shared Channels

You can allow Veeam Backup for Microsoft 365 to back up and restore Microsoft Teams private and shared channels in Microsoft 365 organizations with modern app-only authentication that were added to previous installations of the product. This functionality requires a Microsoft Entra application to be granted the ChannelMember.ReadWrite.All and Files.ReadWrite.All permissions of the Application type.

To update permissions of the Microsoft Entra application, do the following:

1. Edit your Microsoft 365 organization with modern app-only authentication. For more information, see [Editing Organization Settings](vbo_editing_org.md).
2. Select the Use an existing Microsoft Entra ID application option to connect to your Microsoft 365 organization.
3. Click Install to run the Select Certificate wizard.
4. Proceed to any of the following options:

* [Select certificate from the Certificate Store of this server](vbo_installing_certificate.md#selecting_file)
* [Import certificate from a PFX file](vbo_installing_certificate.md#import)

1. Select the Grant the required permissions to this application and register its certificate in Microsoft Entra ID check box to automatically update permissions of the existing Microsoft Entra application. For more information, see [Using Existing Microsoft Entra Application](register_ad_application.md#uea).

Alternatively, you can sign in to Microsoft Identity platform and manually grant this Microsoft Entra application the required permissions. For more information, see [Permissions for Modern App-Only Authentication](ad_app_permissions_sd.md).

Upgrading REST API on Separate Machine

If you use a separate machine with REST API for communicating with Restore Portal, you must manually upgrade the Veeam Backup for Microsoft 365 REST API component on this machine. For more information, see [Upgrading REST API on Separate Machine](restapi_upgrading.md).

Upgrading Backup Infrastructure Components

Once Veeam Backup for Microsoft 365 is upgraded, the following entities will be marked as Out of Date:

* Backup repositories

For information on how to upgrade backup repositories, see [Upgrading Backup Repositories](vbo_upgrading_repository.md).

* Backup proxy servers

For information on how to upgrade backup proxy servers, see [Upgrading Backup Proxy Servers](vbo_upgrading_proxy_server.md)

Consider that a default backup proxy server will be upgraded automatically.

Removing Local Cache Directory

You have created this directory in previous installations of Veeam Backup for Microsoft 365 to store object storage cache that contains backup metadata. During upgrade to version 8, Veeam Backup for Microsoft 365 copies existing metadata to the PersistentCache database created by Veeam Backup for Microsoft 365 on the PostgreSQL instance. For more information, see [Cache](understanding_cache.md).

You can manually remove this directory because Veeam Backup for Microsoft 365 does not use it anymore.

Page updated 8/13/2025

Page content applies to build 8.3.0.2201
