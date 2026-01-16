---
title: "get-vbocommand"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbocommand.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns a set of the available cmdlets.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get all Veeam Backup for Microsoft 365 cmdlets.

|  |
| --- |
| Get-VBOCommand [<CommonParameters>] |

* Get a cmdlet with a specified name.

|  |
| --- |
| Get-VBOCommand [-Name <String>] [<CommonParameters>] |

* Get cmdlets whose names contain a specified noun or verb.

|  |
| --- |
| Get-VBOCommand [-Noun <String>] [-Verb <String>] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of cmdlets available for Veeam Backup for Microsoft 365. You can query the cmdlets by the full name of the necessary cmdlet, or by the verb or noun in the cmdlet name.

For example, the name of the Get-VBOCommand cmdlet consists of the Get verb and the VBOCommand noun. To get this cmdlet, you can search it either by its full name, the Get verb or the VBOCommand noun.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies a name to query cmdlets. The cmdlet will return a cmdlet whose name matches the specified name. | String | False | 0 | True (ByValue, ByPropertyName) |
| Noun | Specifies a noun to query cmdlets. The cmdlet will return a list of cmdlets whose names contain the specified noun. | String | False | Named | True (ByPropertyName) |
| Verb | Specifies a verb to query cmdlets. The cmdlet will return a list of cmdlets whose names contain the specified verb. | String | False | Named | True (ByPropertyName) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Veeam Backup for Microsoft 365 PowerShell Cmdlets

|  |  |
| --- | --- |
| This command returns all available Veeam Backup for Microsoft 365 PowerShell cmdlets.  |  | | --- | | Get-VBOCommand | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Cmdlet by Name

|  |  |
| --- | --- |
| This command returns the Add-VBOJob cmdlet.  |  | | --- | | Get-VBOCommand -Name Add-VBOJob | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Cmdlets by Verb

|  |  |
| --- | --- |
| This command returns a list of cmdlets whose names contain the Get verb.  |  | | --- | | Get-VBOCommand -Verb Get | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Cmdlets that Contain Specific Noun

|  |  |
| --- | --- |
| This command returns a list of cmdlets whose names contain the VBOCommand noun.  |  | | --- | | Get-VBOCommand -Noun VBOCommand | |

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
