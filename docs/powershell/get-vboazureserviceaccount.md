---
title: "Get-VBOAzureServiceAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazureserviceaccount.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# Get-VBOAzureServiceAccount


Short Description

Returns Microsoft Azure service account details.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get Microsoft Azure service account details by the Microsoft Entra application name or description.

|  |
| --- |
| Get-VBOAzureServiceAccount [-Name <String>] [-Description <String>] [<CommonParameters>] |

* Get Microsoft Azure service account details by the service account ID.

|  |
| --- |
| Get-VBOAzureServiceAccount -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of Microsoft Azure service accounts added to Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies an array of Microsoft Entra application names. The cmdlet will return details of Microsoft Azure service accounts associated with the specified Microsoft Entra applications. | String | False | Named | False |
| Description | Specifies a description of Microsoft Azure service account.  Note: To filter objects, you can use \* and ? wildcard characters. | String | False | Named | False |
| Id | Specifies an array of IDs for Microsoft Azure service accounts. The cmdlet will return details of Microsoft Azure service accounts with these IDs. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureServiceAccount](vboazureserviceaccount.md) object that contains Microsoft Azure service account details.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Microsoft Azure Service Account by Microsoft Entra Application Name

|  |  |
| --- | --- |
| This command returns the Microsoft Azure service account details by the name of the associated Microsoft Entra application.  |  | | --- | | Get-VBOAzureServiceAccount -Name "Archiver Appliance App" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Microsoft Azure Service Account by ID

|  |  |
| --- | --- |
| This command returns the Microsoft Azure service account details by the service account ID.  |  | | --- | | Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2 | |


