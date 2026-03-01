---
title: "Considerations and Limitations"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_considerations.html"
last_updated: "2/27/2026"
product_version: "8.3.0.2201"
---

# Considerations and Limitations


This section lists considerations and known limitations in Veeam Backup for Microsoft 365 8.3.

|  |
| --- |
| Note |
| For the complete list of known issues and limitations in Veeam Backup for Microsoft 365 8.3, see [Release Notes](https://helpcenter.veeam.com/rn/veeam_backup_m365_8_3_release_notes.html).  For limitations in Veeam Backup for Microsoft 365 functionality when protecting organizations with modern app-only authentication, see [this Veeam KB article](https://www.veeam.com/kb3146). |

Infrastructure

* Veeam Backup for Microsoft 365 REST API Service and Veeam Backup for Microsoft 365 Service must be started using the Local System account.
* You cannot change the Veeam Backup for Microsoft 365 server name or the server domain without resetting the configuration.

* System date and time in the UTC format must be the same on all machines where the Veeam Backup for Microsoft 365 components, PostgreSQL and the NATS server are installed.

* If the organization has multiple domains, they must be configured as a mesh to cross authenticate to download content from all domains with the service account. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies#multiple-forests-full-mesh-with-optional-galsync).

* Veeam Backup for Microsoft 365 does not support encryption at-rest for the following JET-based backup repositories:

* A local directory on a backup proxy server.
* Direct Attached Storage (DAS) connected to the backup proxy server.
* Storage Area Network (SAN).
* Network Attached Storage (SMB shares version 3.0 or later).

Keep in mind that SMB shares support will be dropped in future versions of Veeam Backup for Microsoft 365.

* For Outlook for Microsoft 365, only the Semi-Annual Enterprise Channel is supported. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/officeupdates/semi-annual-enterprise-channel).
* If the Veeam Backup for Microsoft 365 console and the Veeam Backup for Microsoft 365 server are deployed on different machines, make sure that the server is trusted for delegation. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/microsoft-desktop-optimization-pack/appv-v4/how-to-configure-the-server-to-be-trusted-for-delegation).
* If any of the machines with any of the Veeam Backup for Microsoft 365 components has been renamed (or its FQDN has been changed), or any machine has been added to a different domain, then all the components become unavailable to each other. If any of the listed has occurred on a server that acts as a backup proxy server, then such a server becomes Offline in the Veeam Backup for Microsoft 365 console. To make a server available, re-add it. For more information, see [Adding Backup Proxy Servers](vbo_adding_proxy_server.md).
* IPv6 is not supported for Microsoft Entra China region.
* If you roll back a successful automatic update of the remote Veeam Backup for Microsoft 365 Console and PowerShell components, the Veeam Backup for Microsoft 365 server will not re-update these components.
* Installing Veeam Backup for Microsoft 365 REST API Service on a machine running Veeam Backup for Microsoft 365 Proxy Service is not supported.

Microsoft 365 organizations

* Adding Microsoft 365 organizations using modern authentication method with legacy protocols allowed is not supported.
* Veeam Backup for Microsoft 365 drops support for Microsoft 365 organizations located in Microsoft Entra Germany region. For more information about deprecated limitations, see [Limitations for Microsoft Entra Germany Region](germany.md).
* Microsoft Teams service is not supported for organizations in Microsoft Entra China region.

* Team chats backup is not supported for Microsoft organizations in Microsoft Entra China, US Government DOD and US Government GCC High regions.

* Email notifications about backup and backup copy job results may not work properly in Microsoft Entra China region.

JET-Based Backup Repositories

To save data in JET-based backup repositories, Veeam Backup for Microsoft 365 uses Extensible Storage Engine (ESE) databases, also known as JET Blue.

For storage systems that you can add to the Veeam Backup for Microsoft 365 backup infrastructure, consider the following:

* Block Storage Systems including Direct Attached Storage (DAS)

* Primary Storage Hardware Systems both with and without deduplication or compression are supported. If the storage system uses compression or deduplication, this storage system and its operating system must be listed on the Certified for Windows Server list. For more information, see [this Microsoft article](https://www.windowsservercatalog.com/certification?open=Window+Server+badges).
* Software Defined Storage Systems with deduplication or compression are not supported.
* For Microsoft Windows operating system or other operating systems, built-in deduplication of the file system is not supported.
* A symbolic link that is configured as a mapped drive is not supported.
* Storage volumes that host backup repositories must be formatted with NTFS or ReFS.
* A 3rd party encryption software is not supported for backups in backup repositories. This may lead to unpredictable system behavior and inevitable data loss.

* Backup Target Deduplication Storage

* Based on the format of the used Microsoft JET database, deduplication backup storage appliances are not supported.

* Network Attached Storage (SMB Shares)

* SMB shares version 3.0 are only supported when they are within the Microsoft Exchange Storage definition. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/exchange/plan-and-deploy/deployment-ref/storage-configuration?view=exchserver-2019).
* NFS shares are not supported.

Object Storage Repositories

* Veeam Backup for Microsoft 365 does not support the $root container in Azure Blob storage.
* Veeam Backup for Microsoft 365 does not support Lifecycle policy in data management.
* S3 Compatible device that you add to Veeam Backup for Microsoft 365 must be fully compatible with the AWS S3 operations and support AWS S3 Signature Version 4 standard. For more information about authentication requests, see [this Amazon article](https://docs.aws.amazon.com/AmazonS3/latest/API/sig-v4-authenticating-requests.html).
* Veeam Backup for Microsoft 365 allows you to move data from a local JET-based backup repository to an object storage repository, but not vice versa. For more information, see the [Move-VBOEntityData](https://helpcenter.veeam.com/docs/vbo365/powershell/move-vboentitydata.html?ver=80) section of the Veeam Backup for Microsoft 365 PowerShell Reference.
* Veeam Backup for Microsoft 365 does not support the Versioning feature for Amazon S3 buckets and S3 Compatible buckets unless Object Lock is enabled for buckets and immutability is enabled for an object storage repository.
* Veeam Backup for Microsoft 365 does not support the Versioning feature for Azure storage accounts unless immutability is enabled for an object storage repository.
* Veeam Backup for Microsoft 365 supports only object storage repositories migrated using native Microsoft Azure or AWS services. Migration of object storage repositories using different applications may lead to the corruption of data blobs.
* Veeam Backup for Microsoft 365 cannot correctly process data in object storage repositories whose structure was changed either manually or using a 3rd party application.
* Governance mode is not supported for immutable IBM Cloud Object Storage and Object First repositories.

Backup

General

* Project Web Apps are not supported for backup.
* On-premises service accounts cannot be used for multi-factor authentication.

* Backup of a Microsoft 365 tenant organization is not supported if the initial domain of the organization was changed. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/microsoft-365/admin/setup/domains-faq?view=o365-worldwide#why-do-i-have-an--onmicrosoft-com--domain).
* Backup of dynamic distribution groups is not supported for Microsoft 365 organizations with modern app-only authentication. Members of dynamic distribution groups cannot be resolved.
* You cannot back up data of on-premises Microsoft organizations to an object storage repository associated with a Linux-based backup proxy server or a backup proxy pool that includes a Linux-based backup proxy server.

Exchange Data

* To back up public folder mailboxes, Veeam Backup account must have a valid Exchange Online license and an active mailbox within the Microsoft 365 organization.
* Veeam Backup for Microsoft 365 supports backup of public folder and discovery search mailboxes and determines correctly object type for shared mailboxes in Microsoft 365 organizations with modern app-only authentication. To back up these objects, Veeam Backup for Microsoft 365 needs access to Exchange Online PowerShell. To do this, a Microsoft Entra application requires the Exchange.ManageAsApp permission and the Global Reader role. It is recommended to grant both the permission and the role to the Microsoft Entra application after upgrading Veeam Backup for Microsoft 365 to version 8. For more information, see [Configuring Backup of Public Folder and Discovery Search Mailboxes](after_upgrade.md#pf_mbx).
* To back up user mailboxes, make sure that a mailbox has a valid Microsoft 365 license. Otherwise, such unlicensed mailbox will not be backed up.
* Veeam Backup for Microsoft 365 backs up public folders that are located under the IPM\_SUBTREE folder only.
* You can select only the root public mailbox when backing up public mailboxes. The child folders of the selected public mailbox will be backed up as well.
* If you modify a retention policy tag for a folder, Veeam Backup for Microsoft 365 will perform full synchronization of that folder during the subsequent backup job session. For more information, see [this Microsoft article](https://technet.microsoft.com/en-us/library/dd297955%28v%3Dexchg.160%29.aspx).
* When backing up Microsoft Exchange mailboxes, Veeam Backup for Microsoft 365 does not create a new version of an item if the Read/Unread property of such item was changed. That said, the Read/Unread property of each of the backed-up items always remains exactly the same as it was during the initial backup.
* Veeam Backup for Microsoft 365 does not back up permissions for sharing mailbox folders and Calendar.

SharePoint and OneDrive Data

* To back up SharePoint and OneDrive for Business objects, make sure that a user account has a valid Microsoft 365 license with SharePoint plan enabled. Otherwise, a backup job will fail with the following error: "User %name% does not have a valid Microsoft 365 license with SharePoint plan enabled".
* A SharePoint Site Collection hierarchy is not supported if the root site was not configured. Make sure to configure the root site in advance using a SharePoint site template of your choice. Otherwise, the following error occurs: "Error: Failed to find web template ID for: STS#-1. This organization account might be missing a valid SharePoint license. Web configuration is not complete".

* If a SharePoint item has several versions with identical owshiddenversion values, only the latest version of this item is backed up, all the rest versions are skipped from processing.

* Veeam Backup for Microsoft 365 does not guarantee backup of OneNote notebooks if their size is greater than 2 GB. For more information, see [this Microsoft article](https://support.microsoft.com/en-us/office/restrictions-and-limitations-in-onedrive-and-sharepoint-64883a5d-228e-48f5-b3d2-eb39e07630fa#onenotenotebooks).

* When you perform backup of SharePoint data, Veeam Backup for Microsoft 365 does not back up the following objects:

* External SharePoint lists.

For more information, see [this Microsoft article](https://support.microsoft.com/en-us/office/differences-between-native-and-external-lists-6601eda9-b722-4bf8-a2bf-ce25cf3d2fd0).

* SharePoint folder attachments.
* SharePoint site collection recycle bin.
* SharePoint sites created by Microsoft Loop.

* Archived SharePoint sites.
* SharePoint sites with blocked access.

Microsoft Teams Data

* As part of Microsoft Teams data backup, Veeam Backup for Microsoft 365 backs up only the following types of channel tabs: Website, Planner, Word, Excel, PowerPoint, Visio, PDF, Document Library, OneNote, SharePoint, Stream, Forms, Power BI, Power Automate (ex Flow) and Azure DevOps.

* Team chats backup is only supported for Microsoft 365 organizations with modern app-only authentication. For more information, see [this Veeam KB article](https://www.veeam.com/kb4340).

* When you perform backup of Microsoft Teams data, Veeam Backup for Microsoft 365 does not back up the following objects:

* One-on-one and group chats.

For more information about chats in Microsoft Teams, see [this Microsoft article](https://support.microsoft.com/en-us/office/first-things-to-know-about-chat-in-microsoft-teams-88ed0a06-6b59-43a3-8cf7-40c01f2f92f2).

You can use Veeam Explorer for Microsoft Exchange to explore data from user mailboxes and view chat messages as MSG files. Keep in mind that it works only for backups that have been created before January 31, 2023. For more information, see [this Microsoft article](https://devblogs.microsoft.com/microsoft365dev/restricted-access-to-microsoft-teams-data-via-ews-starts-january-31-2023).

* Audio and video calls.
* Video recordings saved to Microsoft Stream.
* Contacts.
* Calendar: information about meetings and meeting chats.
* Code snippets in posts.
* Audio files in posts.
* Banner notifications in posts.
* Data of applications added as channel tabs (such as Website, Planner, Word, Excel, PowerPoint, Visio, PDF, Document Library, OneNote, SharePoint, Stream, Forms, Power BI, Power Automate and Azure DevOps) and other 3rd party applications if their data does not reside in the SharePoint document library of the team.
* The TeamsMessagesData folder of the group mailbox that belongs to the Microsoft 365 group associated with the backed-up team.

Restore

|  |
| --- |
| Note |
| For more information about limitations that apply when you restore data from backups using Veeam Explorers, see the following sections of the Veeam Explorers User Guide:   * [Veeam Explorer for Microsoft Exchange](https://helpcenter.veeam.com/docs/vbo365/explorers/vex_considerations.html?ver=80) * [Veeam Explorer for Microsoft SharePoint](https://helpcenter.veeam.com/docs/vbo365/explorers/vesp_recovery_specials.html?ver=80) * [Veeam Explorer for Microsoft OneDrive for Business](https://helpcenter.veeam.com/docs/vbo365/explorers/veod_considerations.html?ver=80) * [Veeam Explorer for Microsoft Teams](https://helpcenter.veeam.com/docs/vbo365/explorers/vet_considerations.html?ver=80) |

* SharePoint sites with a red X over the symbol mean that there is an empty sector of the template and supported content is available in the subsites.
* Microsoft Teams messages cannot be restored directly back to Teams.

* Veeam Backup for Microsoft 365 restores public folders that are located under the IPM\_SUBTREE folder only.
* Restore of public folders can be performed to the original location only.

* Bulk restore (restore of multiple objects) using modern authentication with the Microsoft Entra application certificate is not supported for public folder mailboxes. Use the regular per-object restore instead.
* Bulk restore of Exchange mailboxes can be performed to the original location only. Use a single mailbox, folder or item restore if you want to restore such objects to another location.

* To restore In-Place Hold Items of Exchange 2016/2019 mailboxes to the original location, these mailboxes must have In-Place Hold enabled and applied at least once with the DiscoveryHolds system folder creation. Otherwise, restore of In-Place Hold Items will fail with the following error: "Failed to restore In-Place Hold Items. Restore of In-Place Hold Items into Exchange 2013 is not supported".

For more information about enabling In-Place Hold and Litigation Hold, see [this Microsoft article](https://technet.microsoft.com/en-us/library/ff637980%28v%3Dexchg.160%29.aspx).

* Restore of OneNote notebooks from backups of Microsoft SharePoint, Microsoft OneDrive for Business and Microsoft Teams data for organizations with modern app-only authentication is not supported.

* If the size of a OneNote notebook is greater 2 GB, Veeam Backup for Microsoft 365 saves this OneNote notebook as a folder with OneNote items.
* If a SharePoint site includes a hidden list, such list is not displayed in Veeam Explorer for Microsoft SharePoint after a site backup and thus, cannot be restored.
* Before restoring team data using Veeam Explorer for Microsoft Teams or team sites using Veeam Explorer for Microsoft SharePoint for a tenant organization with modern app-only authentication, make sure that a user account used for authorization has access to the root SharePoint site of this tenant organization.

* Restore of an organization data from an object storage repository is not supported if such organization is not added to the Veeam Backup for Microsoft 365 infrastructure.
* When restoring team sites, Veeam Backup for Microsoft 365 does not restore team site owners or Microsoft 365 group members.
* Veeam Backup for Microsoft 365 cannot restore a SharePoint site of a private channel to another location. Restore to its original location is not supported if such a SharePoint site was removed from the Veeam Backup for Microsoft 365 infrastructure.

Related Topics

* [Backup Infrastructure](backup_infrastructure.md)
* [Data Backup](vbo_data_backup.md)
* [Data Restore](vbo_data_restore.md)


