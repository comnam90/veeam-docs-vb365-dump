---
title: "add-vboamazons3objectstoragerepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboamazons3objectstoragerepository.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds Amazon S3 object storage repository to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Add-VBOAmazonS3ObjectStorageRepository](images/icon_note.webp) Note |
| In Veeam Backup for Microsoft 365 8, this cmdlet became deprecated. Use the [New-VBOAmazonS3ObjectStorageSettings](new-vboamazons3objectstoragesettings.md), and [Add-VBOAmazonS3Repository](add-vboamazons3repository.md) or [Add-VBOAmazonS3GlacierRepository](add-vboamazons3glacierrepository.md) cmdlets instead. |

Syntax

This cmdlet provides parameter sets that allow you to:

* Add an object storage repository of the Amazon S3 Standard storage class.

|  |
| --- |
| Add-VBOAmazonS3ObjectStorageRepository -Folder <VBOAmazonS3Folder> -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

* Add an object storage repository of the Amazon S3 Standard or Amazon S3 Standard-Infrequent Access storage class along with the Amazon archiver appliance.

|  |
| --- |
| Add-VBOAmazonS3ObjectStorageRepository -Folder <VBOAmazonS3Folder> [-EnableIAStorageClass] [-ArchiverAppliance <VBOAmazonArchiverAppliance>] -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

* Add an object storage repository of the Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive storage class along with the Amazon archiver appliance.

|  |
| --- |
| Add-VBOAmazonS3ObjectStorageRepository -Folder <VBOAmazonS3Folder> [-EnableLongTerm] [-EnableGlacierDeepArchive] [-EnableGlacierInstantRetrieval] [-ArchiverAppliance <VBOAmazonArchiverAppliance>] -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

Detailed Description

This cmdlet adds Amazon S3 object storage repository to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Folder | Specifies an Amazon S3 folder. Veeam Backup for Microsoft 365 will save backups or backup copies to the specified folder. | Accepts the VBOAmazonS3Folder object.  To get this object, run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. | True | Named | False |
| Name | Specifies a name of Amazon S3 object storage repository. The cmdlet will add an object storage repository with this name. | String | True | Named | False |
| Description | Specifies a description of Amazon S3 object storage repository. The cmdlet will add an object storage repository with this description. | String | False | Named | False |
| SizeLimit | Specifies a soft limit in GB for the object storage repository consumption that can be exceeded temporarily. If the specified limit is exceeded, Veeam Backup for Microsoft 365 will not run a new job.  Permitted values: 1024–1073741824.  Default: 1024  Note: In PowerShell you can specify a soft limit in GB only. | UInt64 | False | Named | False |
| EnableImmutability | Defines that the cmdlet will add the object storage repository to the Veeam Backup for Microsoft 365 infrastructure with the immutability feature enabled. Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity.  For more information about the immutability feature, see the [Immutability](https://helpcenter.veeam.com/docs/vbo365/guide/immutability.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.  Default: False | SwitchParameter | False | Named | False |
| ImmutabilityPeriodDays | Specifies the number of days when your data will be blocked for deletion or modification.  Note: If you set the null or 0 value, data will be blocked for deletion or modification for the same period as the retention period. | Int32 | False | Named | False |
| EnableIAStorageClass | Defines that the cmdlet will enable the Amazon S3 Standard-Infrequent Access storage class for data blocks that are stored in Amazon S3 object storage repository.  Default: False | SwitchParameter | False | Named | False |
| ArchiverAppliance | Specifies the Amazon archiver appliance.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of the general purpose object storage repositories (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) or to any of Amazon S3 Glacier object storage repositories (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes) during backup copy jobs. | Accepts the VBOAmazonArchiverAppliance object.  To create this object, run the [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md) cmdlet. | False | Named | False |
| EnableLongTerm | Defines that the cmdlet will enable adding an object storage repository of one of the following storage classes:   * Amazon S3 Glacier Instant Retrieval * Amazon S3 Glacier Flexible Retrieval * Amazon S3 Glacier Deep Archive   Default: False | SwitchParameter | True | Named | False |
| EnableGlacierDeepArchive | Defines that the cmdlet will enable the Amazon S3 Glacier Deep Archive storage class.  Default: False | SwitchParameter | False | Named | False |
| EnableGlacierInstantRetrieval | Defines that the cmdlet will enable the Amazon S3 Glacier Instant Retrieval storage class.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3ObjectStorageRepository object that contains settings of Amazon S3 object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding Amazon S3 Object Storage

|  |  |
| --- | --- |
| This example shows how to add Amazon S3 object storage repository.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  Add-VBOAmazonS3ObjectStorageRepository -Folder $folder -Name "Documents" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable.  1. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 2. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 3. Run the Add-VBOAmazonS3ObjectStorageRepository cmdlet. Set the $folder variable as the Folder parameter value. Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding Amazon S3 Object Storage with Description

|  |  |
| --- | --- |
| This example shows how to add Amazon S3 object storage repository with description.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  Add-VBOAmazonS3ObjectStorageRepository -Folder $folder -Name "Documents" -Description "Created by Administrator" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 4. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAmazonS3ObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Specify the Name parameter value. * Specify the Description parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Adding Amazon S3 Standard-Infrequent Access Object Storage with Specified Size Limits

|  |  |
| --- | --- |
| This example shows how to add an object storage repository of the Amazon S3 Standard-Infrequent Access storage class. The repository will be added with size limits set to 5120 GB.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  Add-VBOAmazonS3ObjectStorageRepository -Folder $folder -Name "Documents" -EnableIAStorageClass -SizeLimit 5120 |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 4. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAmazonS3ObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Specify the Name parameter value. * Provide the EnableIAStorageClass parameter. * Specify the SizeLimit parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Adding Amazon S3 Glacier Flexible Retrieval Object Storage

|  |  |
| --- | --- |
| This example shows how to add an object storage repository of the Amazon S3 Glacier Flexible Retrieval storage class.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  Add-VBOAmazonS3ObjectStorageRepository -Folder $folder -EnableLongTerm -Name "Archived Documents" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 4. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAmazonS3ObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Provide the EnableLongTerm parameter. * Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Adding Amazon S3 Glacier Instant Retrieval Object Storage with Immutability Enabled

|  |  |
| --- | --- |
| This example shows how to add an object storage repository of the Amazon S3 Glacier Instant Retrieval storage class with the enabled immutability to store backup copies.  |  | | --- | | $account = Get-VBOAmazonS3Account -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3ConnectionSettings -Account $account -RegionType Global  $bucket = Get-VBOAmazonS3Bucket -AmazonS3ConnectionSettings $connection -RegionId eu-north-1 -Name "BucketName2"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  Add-VBOAmazonS3ObjectStorageRepository -Folder $folder -EnableLongTerm -EnableGlacierInstantRetrieval -EnableImmutability -ImmutabilityPeriodDays 60 -Name "BackupCopies" |  Perform the following steps:   1. Run the [Get-VBOAmazonS3Account](get-vboamazons3account.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 2. Run the [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3ConnectionSettings parameter value. Specify the RegionId parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 4. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAmazonS3ObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Provide the EnableLongTerm parameter. * Provide the EnableGlacierInstantRetrieval parameter. * Provide the EnableImmutability parameter. * Specify the ImmutabilityPeriodDays parameter value. * Specify the Name parameter value. |

Related Commands

* [Get-VBOAmazonS3Account](get-vboamazons3account.md)
* [New-VBOAmazonS3ConnectionSettings](new-vboamazons3connectionsettings.md)
* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)
* [Get-VBOAmazonS3Folder](get-vboamazons3folder.md)
* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
