---
title: "Get-VBOServerComponents"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboservercomponents.html"
last_updated: "1/19/2026"
product_version: "8.3.0.2201"
---

# Get-VBOServerComponents


Short Description

Returns components of the Veeam Backup for Microsoft 365 server.

Syntax

|  |
| --- |
| Get-VBOServerComponents [-Name <String>] [-Id <Guid>] [<CommonParameters>] |

Detailed Description

This cmdlet returns the specified components of the Veeam Backup for Microsoft 365 server.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name of the Veeam Backup for Microsoft 365 server component. The cmdlet will return the server component with the specified name. You can get a collection of components of the following types:   * Proxy * Proxy Pool * Controller * Console * PowerShell   Note: This parameter is case-sensitive. | String | False | Named | False |
| Id | Specifies an ID of the Veeam Backup for Microsoft 365 server component. The cmdlet will return component with the specified ID. | Guid | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns an array of the [VBOServerComponent](vboservercomponent.md) objects that contain information about the Veeam Backup for Microsoft 365 server components.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Server Components

|  |  |
| --- | --- |
| This command returns all server components connected to the Veeam Backup for Microsoft 365 console. The cmdlet output will provide the following details on server components: Id, Name, ServerName, IsOnline, ExtendedLoggingEnabled and DistributedTracingEnabled.  |  | | --- | | Get-VBOServerComponents  Id                     : 1c426a3c-aad7-4a26-ad74-0c36e7f8feb4  Name                   : Proxy  ServerName             : ProxyServer01  IsOnline               : True  ExtendedLoggingEnabled : False  DistributedTracingEnabled : False    Id                     : e9454a9e-d0b1-43cf-947e-53631fe49bbd  Name                   : Proxy  ServerName             : ProxyServer02  IsOnline               : True  ExtendedLoggingEnabled : False  DistributedTracingEnabled : False    Id                     : adc79622-7ff2-4055-bc9f-7ae8ebcd87ef  Name                   : Server, PowerShell, Console  ServerName             : BackupServer  IsOnline               : True  ExtendedLoggingEnabled : True  DistributedTracingEnabled : True | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Backup Proxy Servers

|  |  |
| --- | --- |
| This command returns all backup proxy servers connected to the Veeam Backup for Microsoft 365 console. The cmdlet output will provide the following details on backup proxy servers: Id, Name, ServerName, IsOnline, ExtendedLoggingEnabled and DistributedTracingEnabled.  |  | | --- | | Get-VBOServerComponents -Name "Proxy"  Id                     : 1c426a3c-aad7-4a26-ad74-0c36e7f8feb4  Name                   : Proxy  ServerName             : ProxyServer01  IsOnline               : True  ExtendedLoggingEnabled : False  DistributedTracingEnabled : False    Id                     : e9454a9e-d0b1-43cf-947e-53631fe49bbd  Name                   : Proxy  ServerName             : ProxyServer02  IsOnline               : True  ExtendedLoggingEnabled : False  DistributedTracingEnabled : False | |


