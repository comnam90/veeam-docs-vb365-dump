---
title: "remove-vboamazons3account"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboamazons3account.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Removes Amazon S3 storage account credentials from Veeam Backup for Microsoft 365.

Syntax

|  |
| --- |
| Remove-VBOAmazonS3Account -Account <VBOAmazonS3Account> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes Amazon S3 storage account credentials from Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies Amazon S3 storage account credentials that you want to remove. | Accepts the VBOAmazonS3Account object.  To get this object, run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing Amazon S3 Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to remove Amazon S3 storage account credentials.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  Remove-VBOAmazonS3Account -Account $account |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the Remove-VBOAmazonS3Account cmdlet. Set the $account variable as the Account parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing Amazon S3 Storage Account Credentials (Using Pipeline)

|  |  |
| --- | --- |
| This example shows how to remove Amazon S3 storage account credentials.  |  | | --- | | Get-VBOAmazonS3Account | Remove-VBOAmazonS3Account |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. 2. Pipe the cmdlet output to the Remove-VBOAmazonS3Account cmdlet. |

Related Commands

[Get-VBOAmazonS3Account](get-vboamazons3account.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
