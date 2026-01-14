---
title: "set-vboamazons3compatibleaccount"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboamazons3compatibleaccount.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies S3 Compatible storage account credentials.

Syntax

|  |
| --- |
| Set-VBOAmazonS3CompatibleAccount -Account <VBOAmazonS3CompatibleAccount> [-AccessKey <String>] [-SecurityKey <SecureString>] [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies account credentials for the following types of object storage repositories:

* S3 Compatible object storage repository.
* IBM Cloud Object Storage.
* Wasabi Cloud Object Storage.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies S3 Compatible storage account credentials that you want to modify. | Accepts the VBOAmazonS3CompatibleAccount object.  To get this object, run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. | True | Named | False |
| AccessKey | Specifies an access key. The cmdlet will use this key to add S3 Compatible storage account credentials to Veeam Backup for Microsoft 365. | String | False | Named | False |
| SecurityKey | Specifies a secret key. The cmdlet will use this secret key to add the S3 Compatible storage account credentials to Veeam Backup for Microsoft 365. | SecureString | False | Named | False |
| Description | Specifies a description for S3 Compatible storage account credentials. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3CompatibleAccount object that contains S3 Compatible storage account credentials.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Access Key for S3 Compatible Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify an access key for S3 Compatible storage account credentials that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -AccessKey "?Iqws8NewidZydk"  Set-VBOAmazonS3CompatibleAccount -Account $account -AccessKey "%92$sQ}i1qblpQb" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the AccessKey parameter value. Save the result to the $account variable. 2. Run the Set-VBOAmazonS3CompatibleAccount cmdlet. Set the $account variable as the Account parameter value. Specify a new value for the AccessKey parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Security Key for S3 Compatible Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a security key for S3 Compatible storage account credentials that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Set-VBOAmazonS3CompatibleAccount -Account $account -AccessKey "?Iqws8NewidZydk" -SecurityKey $securepassword |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 3. Enter the password. 4. Run the Set-VBOAmazonS3CompatibleAccount cmdlet. Specify the following settings:  * Set the $account variable as the Account parameter value. * Specify the AccessKey parameter value. * Set the $securepassword variable as the SecurityKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Description for S3 Compatible Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a description for S3 Compatible storage account credentials that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  Set-VBOAmazonS3CompatibleAccount -Account $account -Description "Administrator Credential Records" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the Set-VBOAmazonS3CompatibleAccount cmdlet. Set the $account variable as the Account parameter value. Specify the Description parameter value. |

Related Commands

* [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)
* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
