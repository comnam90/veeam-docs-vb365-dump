---
title: "Get-VBOSecuritySettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbosecuritysettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOSecuritySettings


Short Description

Returns security settings.

Syntax

|  |
| --- |
| Get-VBOSecuritySettings [<CommonParameters>] |

Detailed Description

This cmdlet returns security settings. These settings specify an SSL certificate used to establish connection with backup proxy servers in a workgroup.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOSecuritySettings](vbosecuritysettings.md) object that contains security settings.

Example

Getting Veeam Backup for Microsoft 365 Security Settings

This command returns Veeam Backup for Microsoft 365 security settings.

|  |
| --- |
| Get-VBOSecuritySettings |


