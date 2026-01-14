---
title: "disconnect-vboserver"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/disconnect-vboserver.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Ends current PowerShell session with the Veeam Backup for Microsoft 365 server.

Syntax

|  |
| --- |
| Disconnect-VBOServer [<CommonParameters>] |

Detailed Description

This cmdlet ends the current local or remote PowerShell session with the Veeam Backup for Microsoft 365 server. The session can be started, for example, with the [Connect-VBOServer](connect-vboserver.md) cmdlet or from the user interface.

Run the [Connect-VBOServer](connect-vboserver.md) cmdlet to start a new session with the Veeam Backup for Microsoft 365 server.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Stopping Connection to Server

This command ends the current PowerShell session with the Veeam Backup for Microsoft 365 server.

|  |
| --- |
| Disconnect-VBOServer |

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
