---
title: "New-VBOAmazonS3ObjectStorageSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboamazons3objectstoragesettings.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# New-VBOAmazonS3ObjectStorageSettings


Short Description

Defines the Amazon S3 object storage repository settings.

Syntax

|  |
| --- |
| New-VBOAmazonS3ObjectStorageSettings -Folder <VBOAmazonS3Folder> [-ArchiverAppliance <VBOAmazonArchiverAppliance>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOAmazonS3ObjectStorageRepository](vboamazons3objectstoragerepository.md) object. This object contains settings of Amazon S3 object storage repository.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Folder | Specifies an Amazon S3 folder. Veeam Backup for Microsoft 365 will save backups or backup copies to the specified folder. | Accepts the [VBOAmazonS3Folder](vboamazons3folder.md) object.  To get this object, run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. | True | Named | False |
| ArchiverAppliance | Specifies the Amazon archiver appliance.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of the general purpose object storage repositories (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) or to any of Amazon S3 Glacier object storage repositories (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes) during backup copy jobs. | Accepts the [VBOAmazonArchiverAppliance](vboamazonarchiverappliance.md) object.  To create this object, run the [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAmazonS3ObjectStorageRepository](vboamazons3objectstoragerepository.md) object that contains settings of Amazon S3 object storage repository.

Example

Defining Amazon S3 Object Storage Settings

This example shows how to define settings for Amazon S3 object storage repository.

|  |
| --- |
| $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  New-VBOAmazonS3ObjectStorageSettings -Folder $folder |

Perform the following steps:

1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable.
2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable.

1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $bucket variable.
2. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable.
3. Run the New-VBOAmazonS3ObjectStorageSettings cmdlet. Set the $folder variable as the Folder parameter value.

Related Commands

* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)
* [Get-VBOAmazonS3Folder](get-vboamazons3folder.md)
* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)


