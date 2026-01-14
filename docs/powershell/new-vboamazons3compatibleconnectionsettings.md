---
title: "new-vboamazons3compatibleconnectionsettings"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboamazons3compatibleconnectionsettings.html"
last_updated: "8/19/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines connection settings to S3 Compatible object storage repository.

Syntax

|  |
| --- |
| New-VBOAmazonS3CompatibleConnectionSettings -Account <VBOAmazonS3CompatibleAccount> -ServicePoint <String> [-CustomRegionId <String>] [-TrustServerCertificate] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOAmazonS3CompatibleConnectionSettings object. This object contains connection settings to S3 Compatible object storage repository.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Account | Specifies S3 Compatible storage account credentials. The cmdlet will use these storage account credentials to connect to S3 Compatible object storage repository. | Accepts the VBOAmazonS3CompatibleAccount object.  To get this object, run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. | True | Named | False |
| ServicePoint | Specifies the S3 Compatible endpoint address. The cmdlet will use this endpoint address to connect to S3 Compatible object storage repository. | String | True | Named | False |
| CustomRegionId | Specifies an Amazon S3 region where your S3 Compatible object storage repository is located. | String | False | Named | False |
| TrustServerCertificate | Defines that Veeam Backup for Microsoft 365 will trust S3 Compatible self-signed certificates.  If you omit this parameter, Veeam Backup for Microsoft 365 will not trust S3 Compatible self-signed certificates.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3CompatibleConnectionSettings object that defines connection settings to S3 Compatible object storage repository.

Example

Connecting to S3 Compatible Storage

This example shows how to connect to S3 Compatible storage.

|  |
| --- |
| $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000" |

Perform the following steps:

1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable.
2. Run the New-VBOAmazonS3CompatibleConnectionSettings cmdlet. Specify the following settings:

* Set the $account variable as the Account parameter value.
* Specify the ServicePoint parameter value.

Related Commands

[Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)

Page updated 8/19/2024

Page content applies to build 8.3.0.2201
