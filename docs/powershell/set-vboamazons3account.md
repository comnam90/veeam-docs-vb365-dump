---
title: "set-vboamazons3account"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboamazons3account.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies Amazon S3 storage account credentials.

Syntax

|  |
| --- |
| Set-VBOAmazonS3Account -Account <VBOAmazonS3Account> [-AccessKey <String>] [-SecurityKey <SecureString>] [-Description <String>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies Amazon S3 storage account credentials. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies Amazon S3 storage account credentials that you want to modify. | Accepts the VBOAmazonS3Account object.  To get this object, run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. | True | Named | False |
| AccessKey | Specifies an access key. The cmdlet will use this key to add Amazon S3 storage account credentials to Veeam Backup for Microsoft 365. | String | False | Named | False |
| SecurityKey | Specifies a secret key. The cmdlet will use this secret key to add the Amazon S3 storage account credentials to Veeam Backup for Microsoft 365. | SecureString | False | Named | False |
| Description | Specifies a description for Amazon S3 storage account credentials. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3Account object that contains Amazon S3 storage account credentials.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Access Key for Amazon S3 Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify an access key for Amazon S3 storage account credentials that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $account = Get-VBOAmazonS3Account -AccessKey "?Iqws8NewidZydk"  Set-VBOAmazonS3Account -Account $account -AccessKey "%92$sQ}i1qblpQb" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the AccessKey parameter value. Save the result to the $account variable. 2. Run the Set-VBOAmazonS3Account cmdlet. Set the $account variable as the Account parameter value. Specify the AccessKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Security Key for Amazon S3 Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a security key for Amazon S3 storage account credentials that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $securepassword = Read-Host "Enter your password" -AsSecureString  Enter your password: \*\*\*\*\*\*\*\*\*\*  Set-VBOAmazonS3Account -Account $account -AccessKey "?Iqws8NewidZydk" -SecurityKey $securepassword |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5) cmdlet. Specify the message that the console will display as a prompt. Provide the AsSecureString parameter. Save the result to the $securepassword variable. 3. Enter the password. 4. Run the Set-VBOAmazonS3Account cmdlet. Specify the following settings:  * Set the $account variable as the Account parameter value. * Specify the AccessKey parameter value. * Set the $securepassword variable as the SecurityKey parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Description for Amazon S3 Storage Account Credentials

|  |  |
| --- | --- |
| This example shows how to modify a description for Amazon S3 storage account credentials that are added to Veeam Backup for Microsoft 365.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  Set-VBOAmazonS3Account -Account $account -Description "Administrator Credential Records" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the ID parameter value. Save the result to the $account variable. 2. Run the Set-VBOAmazonS3Account cmdlet. Set the $account variable as the Account parameter value. Specify the Description parameter value. |

Related Commands

* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [Read-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
