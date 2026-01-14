---
title: "add-vboazureblobobjectstoragerepository"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboazureblobobjectstoragerepository.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds Azure Blob Storage to the Veeam Backup for Microsoft 365 infrastructure.

|  |
| --- |
| ![Add-VBOAzureBlobObjectStorageRepository](images/icon_note.webp) Note |
| In Veeam Backup for Microsoft 365 8, this cmdlet became deprecated. Use the [New-VBOAzureBlobObjectStorageSettings](new-vboazureblobobjectstoragesettings.md), and [Add-VBOAzureBlobRepository](add-vboazureblobrepository.md) or [Add-VBOAzureArchiveRepository](add-vboazurearchiverepository.md) cmdlets instead. |

Syntax

This cmdlet provides parameter sets that allow you to:

* Add Microsoft Azure Blob Storage.

|  |
| --- |
| Add-VBOAzureBlobObjectStorageRepository -Folder <VBOAzureBlobFolder> -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

* Add Microsoft Azure Blob Storage Archive.

|  |
| --- |
| Add-VBOAzureBlobObjectStorageRepository -Folder <VBOAzureBlobFolder> [-EnableLongTerm] -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

* Add Microsoft Azure Blob Storage Archive along with Microsoft Azure subscription required to use the Azure archiver appliance.

|  |
| --- |
| Add-VBOAzureBlobObjectStorageRepository -Folder <VBOAzureBlobFolder> [-EnableLongTerm] -Subscription <VBOAzureSubscription> [-ArchiverAppliance <VBOAzureArchiverAppliance>] -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

* Add Microsoft Azure Blob Storage along with Microsoft Azure subscription required to use the Azure archiver appliance.

|  |
| --- |
| Add-VBOAzureBlobObjectStorageRepository -Folder <VBOAzureBlobFolder> -Subscription <VBOAzureSubscription> [-ArchiverAppliance <VBOAzureArchiverAppliance>] -Name <String> [-Description <String>] [-SizeLimit <UInt64>] [-EnableImmutability] [-ImmutabilityPeriodDays <Int32>] [<CommonParameters>] |

Detailed Description

This cmdlet adds Azure Blob Storage to the Veeam Backup for Microsoft 365 infrastructure.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Folder | Specifies an Azure Blob folder. Veeam Backup for Microsoft 365 will save backups or backup copies to the specified folder. | Accepts the VBOAzureBlobFolder object.  To get this object, run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. | True | Named | False |
| Name | Specifies a name of Azure Blob Storage. The cmdlet will add an object storage repository with this name. | String | True | Named | False |
| Description | Specifies a description of Azure Blob Storage. The cmdlet will add an object storage repository with this description. | String | False | Named | False |
| SizeLimit | Specifies a soft limit in GB for the object storage repository consumption that can be exceeded temporarily. If the specified limit is exceeded, Veeam Backup for Microsoft 365 will not run a new job.  Permitted values: 1024–1073741824.  Default: 1024  Note: In PowerShell you can specify a soft limit in GB only. | UInt64 | False | Named | False |
| EnableImmutability | Defines that the cmdlet will add the object storage repository to the Veeam Backup for Microsoft 365 infrastructure with the immutability feature enabled. Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity.  For more information about the immutability feature, see the [Immutability](https://helpcenter.veeam.com/docs/vbo365/guide/immutability.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.  Default: False | SwitchParameter | False | Named | False |
| ImmutabilityPeriodDays | Specifies the number of days when your data will be blocked for deletion or modification.  Note: If you set the null or 0 value, data will be blocked for deletion or modification for the same period as the retention period. | Int32 | False | Named | False |
| EnableLongTerm | Defines that the cmdlet will enable adding of the Azure Blob Storage Archive access tier.  Default: False | SwitchParameter | True | Named | False |
| Subscription | Specifies a subscription associated with a user account that will be used to access Azure Blob Storage. | Accepts the VBOAzureSubscription object.  To get this object, run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. | True | Named | False |
| ArchiverAppliance | Specifies the Azure archiver appliance.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive during backup copy jobs. | Accepts the VBOAzureArchiverAppliance object.  To create this object, run the [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAzureBlobObjectStorageRepository object that contains settings of Azure Blob Storage.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding Azure Blob Storage

|  |  |
| --- | --- |
| This example shows how to add Azure Blob Storage. The repository will be added with default size limits.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection -Name "ContainerName"  $folder = Get-VBOAzureBlobFolder -Container $container -Name "FolderName"  Add-VBOAzureBlobObjectStorageRepository -Folder $folder -Name "Music" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $container variable. 4. Run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAzureBlobObjectStorageRepository cmdlet. Set the $folder variable as the Folder parameter value. Specify the Name parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding Azure Blob Storage with Description

|  |  |
| --- | --- |
| This example shows how to add Azure Blob Storage with description.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection -Name "ContainerName"  $folder = Get-VBOAzureBlobFolder -Container $container -Name "FolderName"  Add-VBOAzureBlobObjectStorageRepository -Folder $folder -Name "Documents" -Description "Added by Administrator" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $container variable. 4. Run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAzureBlobObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Specify the Name parameter value. * Specify the Description parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Adding Azure Blob Storage with Specified Size Limits

|  |  |
| --- | --- |
| This example shows how to add Azure Blob Storage. The repository will be added with size limits set to 5120 GB.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection -Name "ContainerName"  $folder = Get-VBOAzureBlobFolder -Container $container -Name "FolderName"  Add-VBOAzureBlobObjectStorageRepository -Folder $folder -Name "Documents" -SizeLimit 5120 |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $container variable. 4. Run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAzureBlobObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value. * Specify the Name parameter value. * Specify the SizeLimit parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Adding Azure Blob Storage Archive with Immutability Enabled

|  |  |
| --- | --- |
| This example shows how to add Azure Blob Storage Archive with the enabled immutability to store backup copies.  |  | | --- | | $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection -Name "ContainerName2"  $folder = Get-VBOAzureBlobFolder -Container $container -Name "FolderName"  Add-VBOAzureBlobObjectStorageRepository -Folder $folder -EnableLongTerm -EnableImmutability -ImmutabilityPeriodDays 60 -Name "BackupCopies" |  Perform the following steps:   1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable. 2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable. 3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $container variable. 4. Run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value. Save the result to the $folder variable. 5. Run the Add-VBOAzureBlobObjectStorageRepository cmdlet. Specify the following settings:  * Set the $folder variable as the Folder parameter value.  * Provide the EnableLongTerm parameter. * Provide the EnableImmutability parameter. * Specify the ImmutabilityPeriodDays parameter value.  * Specify the Name parameter value. |

Related Commands

* [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)
* [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md)
* [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md)
* [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md)
* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
