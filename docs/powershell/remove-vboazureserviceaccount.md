---
title: "remove-vboazureserviceaccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboazureserviceaccount.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes Microsoft Azure service accounts.

Syntax

|  |
| --- |
| Remove-VBOAzureServiceAccount -Account <VBOAzureServiceAccount> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes the specified Microsoft Azure Blob service account from Veeam Backup for Microsoft 365. After removing the service account, Veeam Backup for Microsoft 365 will not be able to use the Azure archiver appliance when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies a Microsoft Azure service account that you want to remove. | Accepts the VBOAzureServiceAccount object.  To get this object, run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing Microsoft Azure Service Account

|  |  |
| --- | --- |
| This example shows how to remove the specified Microsoft Azure service account.  |  | | --- | | $account = Get-VBOAzureServiceAccount -Name "Archiver Appliance App"  Remove-VBOAzureServiceAccount -Account $account |  Perform the following steps:   1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. Specify the Name parameter value. Save the result to the $account variable. 2. Run the Remove-VBOAzureServiceAccount cmdlet. Set the $account variable as the Account parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing Microsoft Azure Service Accounts (Using Pipeline)

|  |  |
| --- | --- |
| This example shows how to remove Microsoft Azure Blob service accounts.  |  | | --- | | Get-VBOAzureServiceAccount | Remove-VBOAzureServiceAccount |  Perform the following steps:   1. Run the [Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md) cmdlet. 2. Pipe the cmdlet output to the Remove-VBOAzureServiceAccount cmdlet. |

Related Commands

[Get-VBOAzureServiceAccount](get-vboazureserviceaccount.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
