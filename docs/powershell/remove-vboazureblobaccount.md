---
title: "remove-vboazureblobaccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboazureblobaccount.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes Microsoft Azure Blob Storage account credentials.

Syntax

|  |
| --- |
| Remove-VBOAzureBlobAccount -Account <VBOAzureBlobAccount> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes Microsoft Azure Blob Storage account credentials from Veeam Backup for Microsoft 365. After removing storage account credentials, Veeam Backup for Microsoft 365 will not be able to connect to Microsoft Azure Blob Storage and you will not be able to connect to your Microsoft Azure Blob Storage account.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies Microsoft Azure Blob Storage account credentials that you want to remove. | Accepts the VBOAzureBlobAccount object.  To get this object, run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing Microsoft Azure Blob Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to remove the Microsoft Azure Blob Storage account credentials.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Name "Microsoft Azure Blob"  Remove-VBOAzureBlobAccount -Account $account |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the Remove-VBOAzureBlobAccount cmdlet. Set the $account variable as the Account parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing Microsoft Azure Blob Storage Account Credentials (Using Pipeline)

|  |  |
| --- | --- |
| This example shows how to remove Microsoft Azure Blob Storage account credentials.  |  | | --- | | Get-VBOAzureBlobAccount | Remove-VBOAzureBlobAccount |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. 2. Pipe the cmdlet output to the Remove-VBOAzureBlobAccount cmdlet. |

Related Commands

[Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
