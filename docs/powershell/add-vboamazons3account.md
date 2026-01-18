---
title: "Add-VBOAmazonS3Account"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboamazons3account.html"
last_updated: "12/22/2025"
product_version: "8.3.0.2201"
---

# Add-VBOAmazonS3Account


Short Description

Creates Amazon S3 storage account credentials.

Syntax

|  |
| --- |
| Add-VBOAmazonS3Account -AccessKey <String> -SecurityKey <SecureString> [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOAmazonS3Account](vboamazons3account.md) object. Veeam Backup for Microsoft 365 will use these storage account credentials to access Amazon S3 storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| AccessKey | Specifies an access key. The cmdlet will use this key to add Amazon S3 storage account credentials to Veeam Backup for Microsoft 365. | String | True | Named | False |
| SecurityKey | Specifies a secret key. The cmdlet will use this secret key to add the Amazon storage account credentials to Veeam Backup for Microsoft 365. | SecureString | True | Named | False |
| Description | Specifies a description for Amazon S3 storage account credentials. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAmazonS3Account](vboamazons3account.md) object that contains Amazon S3 storage account credentials.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding Amazon S3 Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to add Amazon S3 storage account credentials to Veeam Backup for Microsoft 365.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAmazonS3Account -AccessKey "867F16FDE95B12DF" -SecurityKey $securepassword |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAmazonS3Account cmdlet. Specify the AccessKey parameter value. Set $securepassword as the SecurityKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding Amazon S3 Storage Account Credentials with Description

|  |  |
| --- | --- |
| This example shows how to add Amazon S3 storage account credentials with a description.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAmazonS3Account -AccessKey "eu7^vuKvvhcrtbP" -SecurityKey $securepassword -Description "Amazon S3 Credential Records" |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAmazonS3Account cmdlet. Specify the following settings:  * Set the $securepassword variable as the SecurityKey parameter value. * Specify the AccessKey parameter value. * Specify the Description parameter value. |

Related Commands

[Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)


