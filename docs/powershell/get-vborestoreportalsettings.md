---
title: "Get-VBORestorePortalSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborestoreportalsettings.html"
last_updated: "3/12/2026"
product_version: "8.4.0.1457"
---

# Get-VBORestorePortalSettings


Short Description

Returns connection settings to access Restore Portal.

Syntax

|  |
| --- |
| Get-VBORestorePortalSettings [<CommonParameters>] |

Detailed Description

This cmdlet returns connection settings to access Restore Portal. These settings specify whether Restore Portal is enabled, an identification number of Microsoft Entra application configured to access Restore Portal and a TLS certificate used for data exchange.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBORestorePortalSettings](vborestoreportalsettings.md) object that contains connection settings to access Restore Portal.

Example

Getting Authentication Settings to Access Restore Portal

This command returns connection settings to access Restore Portal.

|  |
| --- |
| Get-VBORestorePortalSettings |


