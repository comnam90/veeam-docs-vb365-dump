---
title: "get-vboazuresubscription"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboazuresubscription.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns Microsoft Azure subscriptions associated with a user account that will be used to access Azure Blob Storage.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get a subscription by the Microsoft Azure service account and the subscription name.

|  |
| --- |
| Get-VBOAzureSubscription -ServiceAccount <VBOAzureServiceAccount> [-Name <String>] [<CommonParameters>] |

* Get a subscription by the subscription ID.

|  |
| --- |
| Get-VBOAzureSubscription [-Id <String>] [<CommonParameters>] |

* Get a subscription by the Microsoft Entra region.

|  |
| --- |
| Get-VBOAzureSubscription [-DeviceCode] -Region <VBOOffice365Region> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of subscriptions associated with a user account that will be used to access Azure Blob Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ServiceAccount | Specifies a Microsoft Azure service account. The cmdlet will return an array of subscriptions added to this service account. | Accepts the VBOAzureServiceAccount object.  To get this object, run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a subscription name. The cmdlet will return the subscription with this name. | String | False | Named | False |
| Id | Specifies a subscription ID. The cmdlet will return the subscription with this ID. | String | False | Named | False |
| DeviceCode | Defines that the cmdlet will require an authentication code to connect to Microsoft Azure and get Microsoft Azure subscriptions.  Default: False | SwitchParameter | False | Named | False |
| Region | Specifies Microsoft Entra region where Microsoft 365 organization datacenter is located:   * China * Germany * USDefence * USGovernment * Worldwide   Default: Worldwide | VBOOffice365Region | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureSubscription object that contains details on subscriptions associated with a user account that will be used to access Azure Blob Storage.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Microsoft Azure Subscription by Subscription Name

|  |  |
| --- | --- |
| This example shows how to get a Microsoft Azure subscription by the subscription name.  |  | | --- | | $azureacc = Get-VBOAzureServiceAccount -Id f8e5ac3d-d883-4dd8-8de3-a8f315fb6ae2  Get-VBOAzureSubscription -ServiceAccount $azureacc -Name "SubscriptionName" |  Perform the following steps:   1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $azureacc variable. 2. Run the Get-VBOAzureSubscription cmdlet. Set the $azureacc variable as the ServiceAccount parameter value. Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Microsoft Azure Subscription by ID

|  |  |
| --- | --- |
| This command returns a Microsoft Azure subscription by ID.  |  | | --- | | Get-VBOAzureSubscription -Id "06b7354e-518f-4a10-b4c1-98f49d743012" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Microsoft Azure Subscription by Microsoft Entra region

|  |  |
| --- | --- |
| This command returns a Microsoft Azure subscription for the China Microsoft Entra region with prompting the authentication code.  |  | | --- | | Get-VBOAzureSubscription -Region China -DeviceCode:$true | |

Related Commands

[Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
