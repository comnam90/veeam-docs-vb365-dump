---
title: "Remove-VBOAmazonS3CompatibleAccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboamazons3compatibleaccount.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Remove-VBOAmazonS3CompatibleAccount


Short Description

Removes S3 Compatible storage account credentials from Veeam Backup for Microsoft 365.

Syntax

|  |
| --- |
| Remove-VBOAmazonS3CompatibleAccount -Account <VBOAmazonS3CompatibleAccount> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes account credentials from the Veeam Backup for Microsoft 365 infrastructure for the following types of object storage repositories:

* S3 Compatible object storage repository.
* IBM Cloud Object Storage.
* Wasabi Cloud Object Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies S3 Compatible storage account credentials that you want to remove. | Accepts the [VBOAmazonS3CompatibleAccount](vboamazons3compatibleaccount.md) object.  To get this object, run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. | True | Named | True (ByValue) |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Removing S3 Compatible Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to remove S3 Compatible storage account credentials.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  Remove-VBOAmazonS3CompatibleAccount -Account $account |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the Remove-VBOAmazonS3Account cmdlet. Set the $account variable as the Account parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Removing S3 Compatible Storage Account Credentials (Using Pipeline)

|  |  |
| --- | --- |
| This example shows how to remove S3 Compatible storage account credentials.  |  | | --- | | Get-VBOAmazonS3CompatibleAccount | Remove-VBOAmazonS3CompatibleAccount |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. 2. Pipe the cmdlet output to the Remove-VBOAmazonS3CompatibleAccount cmdlet. |

Related Commands

[Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)


