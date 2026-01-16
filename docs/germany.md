---
title: "germany"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/germany.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 drops support for Microsoft 365 organizations located in Microsoft Entra Germany region. For more information about Azure Germany, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/germany/).

|  |
| --- |
| Note |
| You can add organizations located in Microsoft Entra Germany region to Veeam Backup for Microsoft 365, only using the [Add-VBOOrganization](https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboorganization.html?ver=80) cmdlet or the POST /Organizations method. |

Consider the following previously declared limitations that will be deprecated in version 8:

* Veeam Backup for Microsoft 365 does not support adding Microsoft 365 organizations using modern app-only authentication in Microsoft Entra Germany region.

* Veeam Backup for Microsoft 365 does not support Microsoft Teams service and team chats backup for Microsoft organizations in Microsoft Entra Germany region.

* Email notifications about backup and backup copy job results may not work properly in Microsoft Entra Germany region.

Page updated 8/22/2024

Page content applies to build 8.3.0.2201
