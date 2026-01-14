---
title: "get-vboproxy"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboproxy.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns backup proxy servers added to the Veeam Backup for Microsoft 365 infrastructure.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get a list of backup proxy servers by the specified organization.

|  |
| --- |
| Get-VBOProxy [-Organization <VBOOrganization>] [-ExtendedView] [<CommonParameters>] |

* Get a backup proxy server by the server ID.

|  |
| --- |
| Get-VBOProxy -Id <Guid> [-ExtendedView] [<CommonParameters>] |

* Get a backup proxy server by the server DNS name or IP address.

|  |
| --- |
| Get-VBOProxy -Hostname <String> [-ExtendedView] [<CommonParameters>] |

Detailed Description

This cmdlet returns a list of backup proxy servers added to the Veeam Backup for Microsoft 365 backup infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return backup proxy servers that are associated with the specified organization. | Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | True (ByValue) |
| ExtendedView | Note: This parameter will be deprecated in future versions of Veeam Backup for Microsoft 365.  Defines whether the cmdlet will return all parameters of the backup proxy server (if the backup proxy server is online) or exclude from a list the ThrottlingValue and ThreadsNumber parameters.  Default: False | SwitchParameter | False | Named | False |
| Id | Specifies an ID of the backup proxy server. The cmdlet will return the backup proxy server with the specified ID. | Guid | True | Named | False |
| Hostname | Specifies a DNS name or an IP address of the backup proxy server that you want to get. | String | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOProxy object that contains a list of backup proxy servers added to the Veeam Backup for Microsoft 365 backup infrastructure.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Backup Proxy Servers

|  |  |
| --- | --- |
| This command returns all backup proxy servers that are added to the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | Get-VBOProxy | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Backup Proxy Server by ID

|  |  |
| --- | --- |
| This command returns a backup proxy server with the ID d96f55a4-d15d-410b-b0f0-d51d17ccdab6.  |  | | --- | | Get-VBOProxy -Id d96f55a4-d15d-410b-b0f0-d51d17ccdab6 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Backup Proxy Server by IP

|  |  |
| --- | --- |
| This command returns a backup proxy server with the 172.17.53.53 IP address.  |  | | --- | | Get-VBOProxy -Hostname 172.17.53.53 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Backup Proxy Server by Organization

|  |  |
| --- | --- |
| This example shows how to get a backup proxy server associated with the Columbus organization.  |  | | --- | | $org = Get-VBOOrganization -Name "Columbus"  Get-VBOProxy -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable. 2. Run the Get-VBOProxy cmdlet. Set the $org variable as the Organization parameter value. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
