---
title: "New-VBOAzureBlobObjectStorageSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/new-vboazureblobobjectstoragesettings.html"
last_updated: "12/18/2025"
product_version: "8.3.0.2201"
---

# New-VBOAzureBlobObjectStorageSettings


Short Description

Defines the Azure Blob Storage settings.

Syntax

This cmdlet provides parameter sets that allow you to:

* Define Azure Blob Storage settings.

|  |
| --- |
| New-VBOAzureBlobObjectStorageSettings -Folder <VBOAzureBlobFolder> [<CommonParameters>] |

* Define Azure Blob Storage settings by specifying Microsoft Azure subscription and Azure archiver appliance.

|  |
| --- |
| New-VBOAzureBlobObjectStorageSettings -Folder <VBOAzureBlobFolder> -Subscription <VBOAzureSubscription> [-ArchiverAppliance <VBOAzureArchiverAppliance>] [<CommonParameters>] |

Detailed Description

This cmdlet creates the [VBOAzureBlobObjectStorageRepository](vboazureblobobjectstoragerepository.md) object. This object contains settings of Azure Blob Storage.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Folder | Specifies an Azure Blob folder. Veeam Backup for Microsoft 365 will save backups or backup copies to the specified folder. | Accepts the [VBOAzureBlobFolder](vboazureblobfolder.md) object.  To get this object, run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. | True | Named | False |
| Subscription | Specifies a subscription associated with a user account that will be used to access Azure Blob Storage. | Accepts the [VBOAzureSubscription](vboazuresubscription.md) object.  To get this object, run the [Get-VBOAzureSubscription](get-vboazuresubscription.md) cmdlet. | True | Named | False |
| ArchiverAppliance | Specifies the Azure archiver appliance.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive during backup copy jobs. | Accepts the [VBOAzureArchiverAppliance](vboazurearchiverappliance.md) object.  To create this object, run the [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md) cmdlet. | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOAzureBlobObjectStorageRepository](vboazureblobobjectstoragerepository.md) object that contains settings of Azure Blob Storage.

Example

Defining Azure Blob Storage Settings

This example shows how to define settings for Azure Blob Storage.

|  |
| --- |
| $account = Get-VBOAzureBlobAccount -Id 133dae61-cfce-4fe0-8f8d-cbe52bd5612a  $connection = New-VBOAzureBlobConnectionSettings -Account $account -RegionType Global  $container = Get-VBOAzureBlobContainer -ConnectionSettings $connection -Name "ContainerName"  $folder = Get-VBOAzureBlobFolder -Container $container -Name "FolderName"  New-VBOAzureBlobObjectStorageSettings -Folder $folder |

Perform the following steps:

1. Run the [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md) cmdlet. Save the result to the $account variable.
2. Run the [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md) cmdlet. Set the $account variable as the Account parameter value. Specify the RegionType parameter value. Save the result to the $connection variable.
3. Run the [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md) cmdlet. Set the $connection variable as the ConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $container variable.
4. Run the [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md) cmdlet. Set the $container variable as the Container parameter value. Specify the Name parameter value. Save the result to the $folder variable.
5. Run the New-VBOAzureBlobObjectStorageSettings cmdlet. Set the $folder variable as the Folder parameter value.

Related Commands

* [Get-VBOAzureBlobAccount](get-vboazureblobaccount.md)
* [New-VBOAzureBlobConnectionSettings](new-vboazureblobconnectionsettings.md)
* [Get-VBOAzureBlobContainer](get-vboazureblobcontainer.md)
* [Get-VBOAzureBlobFolder](get-vboazureblobfolder.md)
* [Get-VBOAzureSubscription](get-vboazuresubscription.md)
* [New-VBOAzureArchiverAppliance](new-vboazurearchiverappliance.md)


