---
title: "get-vboserver"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboserver.html"
last_updated: "6/3/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns information about the Veeam Backup for Microsoft 365 server.

Syntax

|  |
| --- |
| Get-VBOServer [<CommonParameters>] |

Detailed Description

This cmdlet returns the specified path to the folder that will be used as temporary storage for export and save operations.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Getting Server

This command returns information about the Veeam Backup for Microsoft 365 server.

|  |
| --- |
| Get-VBOServer  TempFolderPath  --------------  C:\TemporaryFolder |

Related Commands

[Set-VBOServer](set-vboserver.md)

Page updated 6/3/2025

Page content applies to build 8.3.0.2201
