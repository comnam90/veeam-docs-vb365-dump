---
title: "Get-VBOVersion"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboversion.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOVersion


Short Description

Returns Veeam Backup for Microsoft 365 version.

Syntax

|  |
| --- |
| Get-VBOVersion [<CommonParameters>] |

Detailed Description

This cmdlet returns Veeam Backup for Microsoft 365 build number.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOVersion](vboversion.md) object that contains details about the Veeam Backup for Microsoft 365 version.

Example

Getting Veeam Backup for Microsoft 365 Version

This command returns Veeam Backup for Microsoft 365 build number.

|  |
| --- |
| Get-VBOVersion  ProductVersion  --------------  8.3.0.XXX |


