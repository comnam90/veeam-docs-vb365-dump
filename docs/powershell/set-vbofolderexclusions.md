---
title: "set-vbofolderexclusions"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbofolderexclusions.html"
last_updated: "5/6/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies folder exclusion settings.

Syntax

|  |
| --- |
| Set-VBOFolderExclusions [-DeletedItems] [-Drafts] [-JunkEmail] [-Outbox] [-SyncIssues] [-LitigationHold] [-InPlaceHold] [<CommonParameters>] |

Detailed Description

This cmdlet modifies folder exclusion settings. Veeam Backup for Microsoft 365 will not process the selected mailbox folder types during backup jobs and will not store the excluded data.

By default, backup jobs will back up all folders from user mailboxes.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOFolderExclusions](images/icon_note.webp) Note |
| Folder exclusion settings are global and will be applied to all backup jobs configured in Veeam Backup for Microsoft 365. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| DeletedItems | Defines that the cmdlet will configure backup jobs not to process the Deleted Items and Recoverable Items mailbox folders.  Default: False | SwitchParameter | False | Named | False |
| Drafts | Defines that the cmdlet will configure backup jobs not to process the Drafts mailbox folder.  Default: False | SwitchParameter | False | Named | False |
| JunkEmail | Defines that the cmdlet will configure backup jobs not to process the Junk Email mailbox folder.  Default: False | SwitchParameter | False | Named | False |
| Outbox | Defines that the cmdlet will configure backup jobs not to process the Outbox mailbox folder.  Default: False | SwitchParameter | False | Named | False |
| SyncIssues | Defines that the cmdlet will configure backup jobs not to process the Sync Issues mailbox folder.  Default: False | SwitchParameter | False | Named | False |
| LitigationHold | Defines that the cmdlet will configure backup jobs not to process items of mailboxes placed on Litigation Hold.  Default: False | SwitchParameter | False | Named | False |
| InPlaceHold | Defines that the cmdlet will configure backup jobs not to process preserved items of mailboxes placed on In-Place Hold.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Excluding Junk Email and Drafts Folders from Processing

This command excludes the Junk Email and Drafts mailbox folders from backup jobs.

|  |
| --- |
| Set-VBOFolderExclusions -JunkEmail -Drafts |

Page updated 5/6/2024

Page content applies to build 8.3.0.2201
