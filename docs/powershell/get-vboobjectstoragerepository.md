---
title: "Get-VBOObjectStorageRepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboobjectstoragerepository.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# Get-VBOObjectStorageRepository


Short Description

Returns object storage repositories added to the Veeam Backup for Microsoft 365 infrastructure

|  |
| --- |
| ![Get-VBOObjectStorageRepository](images/icon_note.webp) Note |
| In Veeam Backup for Microsoft 365 8, this cmdlet became deprecated. Use the [Get-VBORepository](get-vborepository.md) cmdlet instead. |

Syntax

This cmdlet provides parameter sets that allow you to:

* Get an object storage repository by the object storage repository name.

|  |
| --- |
| Get-VBOObjectStorageRepository [-Name <String>] [-LongTerm] [<CommonParameters>] |

* Get an object storage repository by the object storage repository ID.

|  |
| --- |
| Get-VBOObjectStorageRepository -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of object storage repositories added to Veeam Backup for Microsoft 365. You can get the following types of object storage repositories:

* Azure Blob Storage
* Amazon S3 object storage repository
* S3 Compatible object storage repository (including IBM Cloud Object Storage and Wasabi Cloud Object Storage)

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Name | Specifies the object storage repository name. The cmdlet will return object an storage repository with this name. | String | False | Named | False |
| LongTerm | Defines that the cmdlet will return settings for the following object storage repositories:   * Azure Blob Storage Archive access tier * all Amazon S3 Glacier storage classes   Default: True | SwitchParameter | False | Named | False |
| Id | Specifies the object storage repository ID. The cmdlet will return an object storage repository with this ID. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOObjectStorageRepository](vboobjectstoragerepository.md) object that contains an array of object storage repositories added to Veeam Backup for Microsoft 365.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Object Storage Repositories

|  |  |
| --- | --- |
| This command returns all object storage repositories added to the Veeam Backup for Microsoft 365 infrastructure.  |  | | --- | | Get-VBOObjectStorageRepository  Id                    : e0edfac7-27eb-4fa3-a02d-892a7e8e48cb  Name                  : Amazon Archive  Description           : Created by SRV0101\Administrator at 4:54:43 PM  Type                  : AmazonS3  EnableSizeLimit       : False  SizeLimit             : 1024 GB  UsedSpace             : 29.5 MB  FreeSpace             :  IsLongTerm            : True  IsSecondary           :  EnableImmutability    : True  EnableDefragmentation : True  ArchiveStorageClass   : GlacierDeepArchive    Id                    : 074220ce-50bb-4001-b6c3-a2fbb3983c69  Name                  : Azure Archive  Description           : Created by SRV0101\Administrator at 7:01:32 PM  Type                  : AzureBlob  EnableSizeLimit       : False  SizeLimit             : 1024 GB  UsedSpace             : 29.1 MB  FreeSpace             :  IsLongTerm            : True  IsSecondary           :  EnableImmutability    : True  EnableDefragmentation : True    Id                    : 18e534cd-51c1-4bcf-bf7b-f7633d07997b  Name                  : Azure  Description           : Created by SRV0101\Administrator at 6:34:29 PM  Type                  : AzureBlob  EnableSizeLimit       : False  SizeLimit             : 0 GB  UsedSpace             : 44.2 MB  FreeSpace             :  IsLongTerm            : False  IsSecondary           :  EnableImmutability    : False  EnableDefragmentation : True | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Object Storage Repository with Specific Name

|  |  |
| --- | --- |
| This command returns an object storage repository with a name ending with Archive.  |  | | --- | | Get-VBOObjectStorageRepository -Name "\*Archive"  Id                    : e0edfac7-27eb-4fa3-a02d-892a7e8e48cb  Name                  : Amazon Archive  Description           : Created by SRV0101\Administrator at 4:54:43 PM  Type                  : AmazonS3  EnableSizeLimit       : False  SizeLimit             : 1024 GB  UsedSpace             : 29.5 MB  FreeSpace             :  IsLongTerm            : True  IsSecondary           :  EnableImmutability    : True  EnableDefragmentation : True  ArchiveStorageClass   : GlacierDeepArchive    Id                    : 074220ce-50bb-4001-b6c3-a2fbb3983c69  Name                  : Azure Archive  Description           : Created by SRV0101\Administrator at 7:01:32 PM  Type                  : AzureBlob  EnableSizeLimit       : False  SizeLimit             : 1024 GB  UsedSpace             : 29.1 MB  FreeSpace             :  IsLongTerm            : True  IsSecondary           :  EnableImmutability    : True  EnableDefragmentation : True | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Object Storage Repository with Specific ID

|  |  |
| --- | --- |
| This command returns the e0edfac7-27eb-4fa3-a02d-892a7e8e48cb object storage repository added to Veeam Backup for Microsoft 365.  |  | | --- | | Get-VBOObjectStorageRepository -Id e0edfac7-27eb-4fa3-a02d-892a7e8e48cb  Id                    : e0edfac7-27eb-4fa3-a02d-892a7e8e48cb  Name                  : Amazon Archive  Description           : Created by SRV0101\Administrator at 4:54:43 PM  Type                  : AmazonS3  EnableSizeLimit       : False  SizeLimit             : 1024 GB  UsedSpace             : 29.5 MB  FreeSpace             :  IsLongTerm            : True  IsSecondary           :  EnableImmutability    : True  EnableDefragmentation : True  ArchiveStorageClass   : GlacierDeepArchive | |


