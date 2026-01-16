---
title: "new-vboamazons3compatibleobjectstoragesettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboamazons3compatibleobjectstoragesettings.html"
last_updated: "9/13/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Defines the S3 Compatible object storage repository settings.

Syntax

|  |
| --- |
| New-VBOAmazonS3CompatibleObjectStorageSettings -Folder <VBOAmazonS3Folder> [-Type <AddAmazonS3CompatibleObjectStorageType>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the VBOAmazonS3CompatibleObjectStorageSettings object. This object contains settings of S3 Compatible object storage repository, IBM Cloud Object Storage or Wasabi Cloud Object Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Folder | Specifies an S3 Compatible folder. Veeam Backup for Microsoft 365 will save backups or backup copies to the specified folder. | Accepts the VBOAmazonS3Folder object.  To get this object, run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. | True | Named | False |
| Type | Specifies a type of S3 Compatible object storage repository. You can select the following type:   * AmazonS3Compatible * IBMCloud * WasabiCloud   Default: AmazonS3Compatible | AddAmazonS3CompatibleObjectStorageType | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3CompatibleObjectStorageSettings object that contains settings of S3 Compatible object storage repository.

Example

Defining S3 Compatible Object Storage Settings

This example shows how to define settings for S3 Compatible object storage repository.

|  |
| --- |
| $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000" -CustomRegionId eu-north-1 -TrustServerCertificate:$true  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  New-VBOAmazonS3CompatibleObjectStorageSettings -Folder $folder -Type AmazonS3Compatible |

Perform the following steps:

1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable.
2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the ServicePoint parameter value. Specify the CustomRegionId parameter value. Set the true value for the TrustServerCertificate parameter. Save the result to the $connection variable.

1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable.
2. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Specify the necessary parameters. Save the result to the $folder variable.
3. Run the New-VBOAmazonS3CompatibleObjectStorageSettings cmdlet. Set the $folder variable as the Folder parameter value. Set AmazonS3Compatible as the Type parameter value.

Related Commands

* [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)
* [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md)

* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)
* [Get-VBOAmazonS3Folder](get-vboamazons3folder.md)

Page updated 9/13/2024

Page content applies to build 8.3.0.2201
