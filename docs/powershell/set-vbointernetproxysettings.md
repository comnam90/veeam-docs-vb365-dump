---
title: "set-vbointernetproxysettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbointernetproxysettings.html"
last_updated: "5/6/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies global internet proxy server settings.

Syntax

|  |
| --- |
| Set-VBOInternetProxySettings [-UseInternetProxy] [-Hostname <String>] [-Port <UInt16>] [-UseAuthentication] [-Credential <PSCredential>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies global internet proxy server settings configured in Veeam Backup for Microsoft 365.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOInternetProxySettings](images/icon_note.webp) Note |
| This cmdlet requires a PSCredential object. To obtain a PSCredential object, run the [Get-Credential](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.5) cmdlet. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| UseInternetProxy | Defines that Veeam Backup for Microsoft 365 will use an internet proxy server as a gateway.  Default: False | SwitchParameter | False | Named | False |
| Hostname | Specifies a DNS name or an IP address of an internet proxy server. | String | False | Named | False |
| Port | Specifies a port number. The cmdlet will use this port number to connect to the internet proxy server.  Default: 3128. | UInt16 | False | Named | False |
| UseAuthentication | Defines that the internet proxy server requires authentication.  Default: False | SwitchParameter | False | Named | False |
| Credential | Specifies credentials that you want to use for authenticating to the internet proxy server. | PSCredential | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Example

Modifying Global Internet Proxy Server Settings

This command sets global internet proxy server settings.

|  |
| --- |
| Set-VBOInternetProxySettings -UseInternetProxy -Hostname internetProxy.local -Port 3128 |

Page updated 5/6/2024

Page content applies to build 8.3.0.2201
