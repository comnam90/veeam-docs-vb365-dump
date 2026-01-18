---
title: "Set-VBOObjectStorageRepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboobjectstoragerepository.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# Set-VBOObjectStorageRepository


Short Description

Modifies settings of an object storage repository added to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Set-VBOObjectStorageRepository](images/icon_note.webp) Note |
| In Veeam Backup for Microsoft 365 8, this cmdlet became deprecated. Use the [Set-VBOAmazonS3Repository](set-vboamazons3repository.md), [Set-VBOAmazonS3CompatibleRepository](set-vboamazons3compatiblerepository.md), [Set-VBOAmazonS3GlacierRepository](set-vboamazons3glacierrepository.md), [Set-VBOAzureBlobRepository](set-vboazureblobrepository.md) and [Set-VBOAzureArchiveRepository](set-vboazurearchiverepository.md) cmdlets instead. |

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify an object storage repository.

|  |
| --- |
| Set-VBOObjectStorageRepository -ObjectStorageRepository <VBOObjectStorageRepository> [-Name <String>] [-Description <String>] [-EnableSizeLimit] [-SizeLimit <UInt64>] [-TrustServerCertificate] [<CommonParameters>] |

* Modify an object storage repository and enable using of the Amazon or Azure archiver appliance.

|  |
| --- |
| Set-VBOObjectStorageRepository -ObjectStorageRepository <VBOObjectStorageRepository> [-Name <String>] [-Description <String>] [-EnableSizeLimit] [-SizeLimit <UInt64>] [-TrustServerCertificate] [-UseArchiverAppliance] [-Subscription <VBOAzureSubscription>] [-AzureArchiverAppliance <VBOAzureArchiverAppliance>] [-AmazonArchiverAppliance <VBOAmazonArchiverAppliance>] [-IgnoreProxyPoolApplianceAccessValidation] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of an object storage repository added to the Veeam Backup for Microsoft 365 infrastructure. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ObjectStorageRepository | Specifies an object storage repository. The cmdlet will modify settings of this object storage repository. | Accepts the [VBOObjectStorageRepository](vboobjectstoragerepository.md) object.  To get this object, run the [Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md) cmdlet. | True | Named | False |
| Name | Specifies a new name of the object storage repository. The cmdlet will replace the current name with the specified name. | String | False | Named | False |
| Description | Specifies a description of the object storage repository. The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| EnableSizeLimit | Defines that the cmdlet will enable a soft limit in GB for the object storage repository consumption that can be exceeded temporarily.  Use the SizeLimit parameter to specify the soft limit value.  Default: False | SwitchParameter | False | Named | False |
| SizeLimit | For the EnableSizeLimit option.  Specifies a soft limit in GB for the object storage repository consumption that can be exceeded temporarily. If the specified limit is exceeded, Veeam Backup for Microsoft 365 will not run a new job.  Permitted values: 1024–1073741824.  Default: 1024  Note: In PowerShell you can specify a soft limit in GB only. | UInt64 | False | Named | False |
| TrustServerCertificate | Defines that Veeam Backup for Microsoft 365 will trust S3 Compatible self-signed certificates.  If you omit this parameter, Veeam Backup for Microsoft 365 will not trust S3 Compatible self-signed certificates.  Default: False | SwitchParameter | False | Named | False |
| UseArchiverAppliance | Defines that the cmdlet will enable usage of the Amazon or Azure archiver appliance when transferring backed-up data to the object storage repository during backup copy jobs.  Default: False | SwitchParameter | True | Named | False |
| Subscription | Specifies a subscription associated with a user account that will be used to access Azure Blob Storage. The cmdlet will replace the current subscription with the specified subscription. | Accepts the [VBOAzureSubscription](vboazuresubscription.md) object.  To get this object, run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. | False | Named | False |
| AzureArchiverAppliance | Specifies the Azure archiver appliance. The cmdlet will replace the current Azure archiver appliance with the specified one.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive during backup copy jobs. | Accepts the [VBOAzureArchiverAppliance](vboazurearchiverappliance.md) object.  To create this object, run the [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md) cmdlet. | False | Named | False |
| AmazonArchiverAppliance | Specifies the Amazon archiver appliance. The cmdlet will replace the current Amazon archiver appliance with the specified one.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of the general purpose object storage repositories (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) or to any of Amazon S3 Glacier object storage repositories (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes) during backup copy jobs. | Accepts the [VBOAmazonArchiverAppliance](vboamazonarchiverappliance.md) object.  To create this object, run the [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md) cmdlet. | False | Named | False |
| IgnoreProxyPoolApplianceAccessValidation | Defines that the cmdlet will ignore check whether backup proxy servers that belong to the associated backup proxy pool can access the archiver appliance.  Default: False  Note: This parameter is not applicable for S3 Compatible object storage repositories. | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOObjectStorageRepository](vboobjectstoragerepository.md) object that contains an array of object storage repositories added to Veeam Backup for Microsoft 365.

Example

Modifying Soft Limit for Object Storage Repository

This example shows how to modify a soft limit for the Azure Backup object storage repository.

|  |
| --- |
| $repository = Get-VBOObjectStorageRepository -Name "Azure Backup"  Set-VBOObjectStorageRepository -ObjectStorageRepository $repository -SizeLimit 2048 |

Perform the following steps:

1. Run the [Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the Set-VBOObjectStorageRepository cmdlet. Set the $repository variable as the ObjectStorageRepository parameter value. Specify the SizeLimit parameter value.

Related Commands

* [Get-VBOObjectStorageRepository](get-vboobjectstoragerepository.md)
* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)
* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)
* [Get-VBOAzureSubscription](get-vboazuresubscription.md)


