---
title: "add-vboamazons3compatibleaccount"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboamazons3compatibleaccount.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates S3 Compatible storage account credentials.

Syntax

|  |
| --- |
| Add-VBOAmazonS3CompatibleAccount -AccessKey <String> -SecurityKey <SecureString> [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOAmazonS3CompatibleAccount object. This object contains storage account credentials for the following types of object storage repositories:

* S3 Compatible object storage repository.
* IBM Cloud Object Storage.
* Wasabi Cloud Object Storage.

Veeam Backup for Microsoft 365 will use these storage account credentials to access these object storage repositories.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| AccessKey | Specifies an access key. The cmdlet will use this key to add S3 Compatible storage account credentials to Veeam Backup for Microsoft 365. | String | True | Named | False |
| SecurityKey | Specifies a secret key. The cmdlet will use this key to add S3 Compatible storage account credentials to Veeam Backup for Microsoft 365. | SecureString | True | Named | False |
| Description | Specifies a description for S3 Compatible storage account credentials. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3CompatibleAccount object that contains S3 Compatible storage account credentials.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding S3 Compatible Credentials

|  |  |
| --- | --- |
| This example shows how to add S3 Compatible storage account credentials to Veeam Backup for Microsoft 365.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAmazonS3CompatibleAccount -AccessKey "867F16FDE95B12DF" -SecurityKey $securepassword |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAmazonS3CompatibleAccount cmdlet. Specify the AccessKey parameter value. Set $securepassword as the SecurityKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding S3 Compatible Credentials with Description

|  |  |
| --- | --- |
| This example shows how to add S3 Compatible storage account credentials with a description.  |  | | --- | | $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Add-VBOAmazonS3CompatibleAccount -AccessKey "eu7^vuKvvhcrtbP" -SecurityKey $securepassword -Description "S3 Compatible Credential Records" |  Perform the following steps:   1. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 2. Enter the password. 3. Run the Add-VBOAmazonS3CompatibleAccount cmdlet. Specify the following settings:  * Set $securepassword as the SecurityKey parameter value. * Specify the AccessKey parameter value. * Specify the Description parameter value. |

Related Commands

[Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
