---
title: "set-vboservercomponents"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboservercomponents.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Enables or disables the extended logging mode and distributed tracing for an array of the Veeam Backup for Microsoft 365 server components.

Syntax

|  |
| --- |
| Set-VBOServerComponents -Components <VBOServerComponent[]> [-EnableExtendedLogging] [-EnableDistributedTracing] [<CommonParameters>] |

Detailed Description

This cmdlet enables or disables the extended logging mode and distributed tracing for one or several Veeam Backup for Microsoft 365 server components. Extended log records contain additional information such as more detailed description of operations performed during the backup and restore processes, as well as more detailed description of items processed during backup and restore. Distributed tracing tracks requests to the Veeam Backup for Microsoft 365 backup infrastructure components and allows you to analyze the activity of services.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Components | Specifies an array of the Veeam Backup for Microsoft 365 server components. The cmdlet will enable the extended logging mode and distributed tracing for these components.  Note: The extended logging mode and distributed tracing will not be modified for components that are not specified in the VBOServerComponent[] object. | Accepts the VBOServerComponent[] object.  To get this object, run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. | True | Named | True (ByValue) |
| EnableExtendedLogging | Enables the extended logging mode for an array of the Veeam Backup for Microsoft 365 server components.  Default: False  Note: To disable the extended logging mode for an array of components, you must set the false value for this parameter. | SwitchParameter | False | Named | False |
| EnableDistributedTracing | Enables distributed tracing for an array of the Veeam Backup for Microsoft 365 server components.  Default: False  Note: To disable distributed tracing for an array of components, you must set the false value for this parameter. | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Enabling Extended Logging Mode for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to enable the extended logging mode for the 06b7354e-518f-4a10-b4c1-98f49d743012 backup proxy server.  |  | | --- | | $proxy = Get-VBOServerComponents -Name Proxy -Id 06b7354e-518f-4a10-b4c1-98f49d743012  Set-VBOServerComponents -Components $proxy -EnableExtendedLogging:$true |  Perform the following steps:   1. Run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. Specify the Name parameter value. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the Set-VBOServerComponents cmdlet. Set the $proxy variable as the Components parameter value. Set the true value for the EnableExtendedLogging parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Enabling Extended Logging Mode for All Backup Proxy Servers [Using Pipeline]

|  |  |
| --- | --- |
| This example shows how to enable the extended logging mode for all backup proxy servers.  |  | | --- | | Get-VBOServerComponents | Where-Object -FilterScript {$\_.Name -eq "Proxy"} | Set-VBOServerComponents -EnableExtendedLogging:$true |  Perform the following steps:   1. Run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. 2. Pipe the cmdlet output to the [Where-Object](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.5) cmdlet. Specify the script block value for the FilterScript parameter. 3. Pipe the cmdlet output to the Set-VBOServerComponents cmdlet. Set the true value for the EnableExtendedLogging parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Disabling Extended Logging Mode for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to disable the extended logging mode for the b8451910-672f-4eec-bfbe-6eba83b91abb backup proxy server.  |  | | --- | | $proxy = Get-VBOServerComponents -Name Proxy -Id b8451910-672f-4eec-bfbe-6eba83b91abb  Set-VBOServerComponents -Components $proxy -EnableExtendedLogging:$false |  Perform the following steps:   1. Run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. Specify the Name parameter value. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the Set-VBOServerComponents cmdlet. Set the $proxy variable as the Components parameter value. Set the false value for the EnableExtendedLogging parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Enabling Distributed Tracing for Backup Proxy Server

|  |  |
| --- | --- |
| This example shows how to enable distributed tracing for the 06b7354e-518f-4a10-b4c1-98f49d743012 backup proxy server.  |  | | --- | | $proxy = Get-VBOServerComponents -Name Proxy -Id 06b7354e-518f-4a10-b4c1-98f49d743012  Set-VBOServerComponents -Components $proxy -EnableDistributedTracing:$true |  Perform the following steps:   1. Run the [Get-VBOServerComponents](get-vboservercomponents.md) cmdlet. Specify the Name parameter value. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the Set-VBOServerComponents cmdlet. Set the $proxy variable as the Components parameter value. Set the true value for the EnableDistributedTracing parameter. |

Related Commands

* [Get-VBOServerComponents](get-vboservercomponents.md)
* [Where-Object](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
