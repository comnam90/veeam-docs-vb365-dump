---
title: "connect-vboserver"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/connect-vboserver.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Connects to the Veeam Backup for Microsoft 365 server.

Syntax

|  |
| --- |
| Connect-VBOServer [-Server <String>] [-Port <Int32>] [-Credential <PSCredential>] [<CommonParameters>] |

Detailed Description

This cmdlet creates a connection with a local or remote Veeam Backup for Microsoft 365 server. The connection starts the Veeam Backup for Microsoft 365 PowerShell session. During the session you can perform all operations available with Veeam Backup for Microsoft 365 PowerShell.

If you do not specify the server, you will connect to the local Veeam Backup for Microsoft 365 server.

Within one session you can connect to one Veeam Backup for Microsoft 365 server. To connect to another Veeam Backup for Microsoft 365 server you need to close the current session. Run the [Disconnect-VBOServer](disconnect-vboserver.md) cmdlet to stop the session with the current Veeam Backup for Microsoft 365 server.

|  |
| --- |
| ![Connect-VBOServer](images/icon_note.webp) Note |
| This cmdlet requires a PSCredential object. To obtain a PSCredential object, run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Server | Specifies the Veeam Backup for Microsoft 365 server. The cmdlet will connect to this server.  Default: 127.0.0.1 | String | False | Named | False |
| Port | Specifies a port number. The cmdlet will use this port number to connect to Veeam Backup for Microsoft 365.  Default: 9191 | Int32 | False | Named | False |
| Credential | Specifies credentials that you want to use for authenticating to the Veeam Backup for Microsoft 365 server.  If you do not provide this parameter, the cmdlet will use the current account credentials. | PSCredential | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Connecting to Server

|  |  |
| --- | --- |
| This command connects to the Veeam Backup for Microsoft 365 server with the following settings:   * The server IP address is 172.13.53.53. * To connect to the server, the cmdlet will use the current account credentials.   |  | | --- | | Connect-VBOServer -Server "172.13.53.53" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Connecting to Server Using Specific Credentials

|  |  |
| --- | --- |
| This example shows how to connect to the Veeam Backup for Microsoft 365 server with the following settings:   * The server IP address is 172.17.53.58. * To connect to the server, the cmdlet will use the credentials that you provide.   |  | | --- | | $creds = Get-Credential  Connect-VBOServer -Server "172.17.53.58" -Credential $creds |  Perform the following steps:   1. Run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. Enter the credentials you want to use to connect to the Veeam Backup for Microsoft 365 server. Save the result to the $creds variable. 2. Run the Connect-VBOServer cmdlet. Set the $creds variable as the Credential parameter value. |

Related Commands

[Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
