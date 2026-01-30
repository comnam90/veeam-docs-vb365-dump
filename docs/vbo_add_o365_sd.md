---
title: "Step 2. Select Organization Deployment Type"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_add_o365_sd.html"
last_updated: "10/7/2025"
product_version: "8.3.0.2201"
---

# Step 2. Select Organization Deployment Type


At this step of the wizard, select a deployment type and Microsoft Online services whose data you want to protect.

|  |
| --- |
| Note |
| Veeam Backup for Microsoft 365 backs up Microsoft Teams messages using Microsoft Graph Teams Export APIs. For more information about team chats backup, see [Team Chats Backup](vbo_object_types.md#team_chats). |

To select an organization deployment type and Microsoft Online services whose data you want to protect, do the following:

1. From the Select organization deployment type drop-down list, select Microsoft 365.
2. If you want to back up Exchange Online data, select the Exchange Online check box.
3. If you want to back up SharePoint Online and OneDrive for Business data, select the SharePoint Online and OneDrive for Business check box.
4. If you want to back up Microsoft Teams data, select the Microsoft Teams check box.

You can select this check box only if both Exchange Online and SharePoint Online and OneDrive for Business check boxes are selected.

1. If you want to back up team chats, select the Teams chats check box.

This check box is available only if the Microsoft Teams check box is selected. For more information about team chats backup, see [Team Chats Backup](vbo_object_types.md#team_chats).

|  |
| --- |
| Note |
| Consider the following:   * Microsoft Teams service is not supported for organizations in Microsoft Entra China region. * Team chats backup is not supported for Microsoft organizations in Microsoft Entra China, US Government DOD and US Government GCC High regions. |

[![Select Organization Deployment Type](images/new_o365_step_one.webp)](images/new_o365_step_one.webp "Select Organization Deployment Type")


