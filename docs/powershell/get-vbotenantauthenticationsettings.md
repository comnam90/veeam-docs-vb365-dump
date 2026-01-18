---
title: "Get-VBOTenantAuthenticationSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbotenantauthenticationsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOTenantAuthenticationSettings


Short Description

Returns the Veeam Backup for Microsoft 365 tenant authentication settings.

Syntax

|  |
| --- |
| Get-VBOTenantAuthenticationSettings [<CommonParameters>] |

Detailed Description

This cmdlet returns tenant authentication settings configured for Veeam Backup for Microsoft 365.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOTenantAuthenticationSettings](vbotenantauthenticationsettings.md) object that contains the Veeam Backup for Microsoft 365 tenant authentication settings.

Example

Getting Tenant Authentication Settings

This command returns tenant authentication settings configured for Veeam Backup for Microsoft 365.

|  |
| --- |
| Get-VBOTenantAuthenticationSettings |


