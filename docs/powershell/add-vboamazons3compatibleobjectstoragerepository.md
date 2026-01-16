---
title: "add-vboamazons3compatibleobjectstoragerepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboamazons3compatibleobjectstoragerepository.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds S3 Compatible object storage repository to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Add-VBOAmazonS3CompatibleObjectStorageRepository](images/icon_note.webp) Note |
| In Veeam Backup for Microsoft 365 8, this cmdlet became deprecated. Use the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) and [Add-VBOAmazonS3CompatibleRepository](add-vboamazons3compatiblerepository.md) cmdlets instead. |

Syntax

|  |
| --- |
| Add-VBOAmazonS3CompatibleObjectStorageRepository -Folder <VBOAmazonS3Folder> [-Type <AddAmazonS3CompatibleObjectStorageType>] -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

Detailed Description

This cmdlet adds S3 Compatible object storage repository, IBM Cloud Object Storage or Wasabi Cloud Object Storage to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Folder | Specifies an S3 Compatible folder. Veeam Backup for Microsoft 365 will save backups or backup copies to the specified folder. | Accepts the VBOAmazonS3Folder object.  To get this object, run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. | True | Named | False |
| Type | Specifies a type of S3 Compatible object storage repository. The cmdlet will add an object storage repository of one of the following types:   * AmazonS3Compatible * IBMCloud * WasabiCloud | AddAmazonS3CompatibleObjectStorageType | False | Named | False |
| Name | Specifies a name of S3 Compatible object storage repository. The cmdlet will add an object storage repository with this name. | String | True | Named | False |
| Description | Specifies a description of S3 Compatible object storage repository. The cmdlet will add an object storage repository with this description. | String | False | Named | False |
| SizeLimit | Specifies a soft limit in GB for the object storage repository consumption that can be exceeded temporarily. If the specified limit is exceeded, Veeam Backup for Microsoft 365 will not run a new job.  Permitted values: 1024–1073741824.  Default: 1024  Note: In PowerShell you can specify a soft limit in GB only. | UInt64 | False | Named | False |
| EnableImmutability | Defines that the cmdlet will add the object storage repository to the Veeam Backup for Microsoft 365 infrastructure with the immutability feature enabled. Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity.  For more information about the immutability feature, see the [Immutability](https://helpcenter.veeam.com/docs/vbo365/guide/immutability.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.  Default: False | SwitchParameter | False | Named | False |
| ImmutabilityPeriodDays | Specifies the number of days when your data will be blocked for deletion or modification.  Note: If you set the null or 0 value, data will be blocked for deletion or modification for the same period as the retention period. | Int32 | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3CompatibleObjectStorageRepository object that contains settings of S3 Compatible object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding S3 Compatible Object Storage

|  |  |
| --- | --- |
| This example shows how to add S3 Compatible object storage repository.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "Reports 09"  Add-VBOAmazonS3CompatibleObjectStorageRepository -Folder $folder -Type AmazonS3Compatible -Name "Documents" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable.  1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable. 2. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Specify the necessary parameters. Save the result to the $folder variable. 3. Run the Add-VBOAmazonS3CompatibleObjectStorageRepository cmdlet. Set the $folder variable as the Folder parameter value. Set AmazonS3Compatible as the Type parameter value. Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding S3 Compatible Object Storage with Description

|  |  |
| --- | --- |
| This example shows how to add S3 Compatible object storage repository with description.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "Reports 08"  Add-VBOAmazonS3CompatibleObjectStorageRepository -Folder $folder -Name "Documents" -Description "Created by Administrator" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable. 4. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Specify the necessary parameters. Save the result to the $folder variable. 5. Run the Add-VBOAmazonS3CompatibleObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Specify the Name parameter value. * Specify the Description parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Adding S3 Compatible Object Storage with Specified Size Limits

|  |  |
| --- | --- |
| This example shows how to add S3 Compatible object storage repository. The repository will be added with size limits set to 5120 GB.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "Reports 07"  Add-VBOAmazonS3CompatibleObjectStorageRepository -Folder $folder -Name "Documents" -SizeLimit 5120 |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable. 4. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Specify the necessary parameters. Save the result to the $folder variable. 5. Run the Add-VBOAmazonS3CompatibleObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Specify the Name parameter value. * Specify the SizeLimit parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Adding S3 Compatible Object Storage of IBMCloud Type with Immutability Enabled

|  |  |
| --- | --- |
| This example shows how to add S3 Compatible object storage repository of the IBMCloud type with the enabled immutability.  |  | | --- | | $account = Get-VBOAmazonS3CompatibleAccount -Id 1dfc5af0-2605-47ac-94d8-13dea4d14608  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName2"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "Reports 10"  Add-VBOAmazonS3CompatibleObjectStorageRepository -Folder $folder -Type IBMCloud -Name "NewBackups" -EnableImmutability -ImmutabilityPeriodDays 60 |  Perform the following steps:   1. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable.  1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Specify the necessary parameters. Save the result to the $bucket variable. 2. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Specify the necessary parameters. Save the result to the $folder variable. 3. Run the Add-VBOAmazonS3CompatibleObjectStorageRepository cmdlet. Set the $folder variable as the Folder parameter value. Set IBMCloud as the Type parameter value. Specify the Name parameter value. Provide the EnableImmutability parameter. Specify the ImmutabilityPeriodDays parameter value. |

Related Commands

* [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)
* [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md)

* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)
* [Get-VBOAmazonS3Folder](get-vboamazons3folder.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
