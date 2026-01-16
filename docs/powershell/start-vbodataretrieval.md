---
title: "start-vbodataretrieval"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/start-vbodataretrieval.html"
last_updated: "2/25/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates and starts retrieval jobs.

|  |
| --- |
| ![Start-VBODataRetrieval](images/icon_note.webp) Note |
| Data retrieval is unavailable for Amazon S3 Glacier Instant Retrieval storage class. You can explore and restore data directly from backup copies using Veeam Explorers. |

Syntax

This cmdlet provides parameter sets that allow you to:

* Create and start a retrieval job to retrieve Exchange data from Azure Blob Storage Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AzureArchiveRetrievalPolicy <VBOAzureArchiveRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-Mailbox <VBOMailboxData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve OneDrive data from Azure Blob Storage Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AzureArchiveRetrievalPolicy <VBOAzureArchiveRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-OneDrive <VBOOneDriveData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve SharePoint data from Azure Blob Storage Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AzureArchiveRetrievalPolicy <VBOAzureArchiveRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-Site <VBOSiteData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve Teams data from Azure Blob Storage Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AzureArchiveRetrievalPolicy <VBOAzureArchiveRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-Team <VBOTeamData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve Exchange data from Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AmazonS3GlacierRetrievalPolicy <VBOAmazonS3GlacierRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-Mailbox <VBOMailboxData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve OneDrive data from Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AmazonS3GlacierRetrievalPolicy <VBOAmazonS3GlacierRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-OneDrive <VBOOneDriveData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve SharePoint data from Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AmazonS3GlacierRetrievalPolicy <VBOAmazonS3GlacierRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-Site <VBOSiteData[]>] [<CommonParameters>] |

* Create and start a retrieval job to retrieve Teams data from Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive.

|  |
| --- |
| Start-VBODataRetrieval -RestorePoint <VBORestorePoint> -AvailabilityPeriodDays <Int32> [-Name <String>] [-Description <String>] -AmazonS3GlacierRetrievalPolicy <VBOAmazonS3GlacierRetrievalPolicy> [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [-ShowDeleted] [-ShowAllVersions] [-Team <VBOTeamData[]>] [<CommonParameters>] |

Detailed Description

This cmdlet creates and starts a retrieval job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| RestorePoint | Specifies a restore point stored in Veeam Backup for Microsoft 365 for the object storage repository that was specified as a target for backup copy jobs. The cmdlet will create and start a retrieval job to retrieve backed-up data from this restore point. | Accepts the VBORestorePoint object.  To get this object, run the [Get-VBORestorePoint](get-vborestorepoint.md) cmdlet. | True | Named | True (ByValue) |
| AvailabilityPeriodDays | Specifies the number of days during which the retrieved backed-up data will be available to explore and restore using Veeam Explorers.  Default: 1 | Int32 | True | Named | False |
| Name | Specifies a retrieval job name. The cmdlet will add a retrieval job with this name. | String | False | Named | False |
| Description | Specifies a description of the retrieval job. | String | False | Named | False |
| AzureArchiveRetrievalPolicy | Specifies a retrieval policy that you want to use for Azure Blob Storage Archive. The cmdlet will create a retrieval job and apply the specified retrieval policy. You can select the following retrieval policies:   * StandardPriority * HighPriority   Note: Data retrieval cost varies depending on the desired speed of the data retrieval process. | VBOAzureArchiveRetrievalPolicy | True | Named | False |
| EnableExpirationNotification | Defines that Veeam Backup for Microsoft 365 will notify you when the availability period is about to end.  Default: False | SwitchParameter | False | Named | False |
| ExpirationHoursThreshold | For the EnableExpirationNotification option.  Specifies how many hours should remain before the retrieved backed-up data expires to send a notification by email. | Int32 | False | Named | False |
| ShowDeleted | Defines that Veeam Backup for Microsoft 365 will retrieve items that have been removed by user before the specified date.  Default: False | SwitchParameter | False | Named | False |
| ShowAllVersions | Defines that Veeam Backup for Microsoft 365 will retrieve all versions of items that have been modified by user before the specified date.  Default: False | SwitchParameter | False | Named | False |
| Mailbox | Specifies an array of mailboxes whose backed-up data you want to retrieve. The cmdlet will create and start a retrieval job to retrieve data for these mailboxes. | VBOMailboxData[] | False | Named | False |
| OneDrive | Specifies an array of OneDrives whose backed-up data you want to retrieve. The cmdlet will create and start a retrieval job to retrieve data for these OneDrives. | VBOOneDriveData[] | False | Named | False |
| Site | Specifies an array of SharePoint sites whose backed-up data you want to retrieve. The cmdlet will create and start a retrieval job to retrieve data for these sites. | VBOSiteData[] | False | Named | False |
| Team | Specifies an array of teams whose backed-up data you want to retrieve. The cmdlet will create and start a retrieval job to retrieve data for these teams. | VBOTeamData[] | False | Named | False |
| AmazonS3GlacierRetrievalPolicy | Specifies a retrieval policy that you want to use for Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes. The cmdlet will create a retrieval job and apply the specified retrieval policy. You can select the following retrieval policies:   * Expedited * Standard * Bulk   Note: Data retrieval cost varies depending on the desired speed of the data retrieval process.  The Expedited policy is unavailable for Amazon S3 Glacier Deep Archive. | VBOAmazonS3GlacierRetrievalPolicy | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBODataRetrieval object that contains settings for a retrieval job.

Example

Starting Retrieval Job to Retrieve Mailbox Data

This example shows how to create and start the retrieval job that will retrieve mailbox data from Azure Blob Storage Archive.

|  |
| --- |
| $repository = Get-VBORepository -Name "Azure Archive Storage"  $mailbox = Get-VBOEntityData -Repository $repository -Type Mailbox -Name "User Mailbox"  $restorepoint = Get-VBORestorePoint -Repository $repository -Latest  Start-VBODataRetrieval -RestorePoint $restorepoint -AvailabilityPeriodDays 5 -AzureArchiveRetrievalPolicy HighPriority -Name "ABC User Mailbox" -EnableExpirationNotification -ExpirationHoursThreshold 2 -Mailbox $mailbox |

Perform the following steps:

1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable.
2. Run the [Get-VBOEntityData](get-vboentitydata.md) cmdlet. Set the $repository variable as the Repository parameter value. Specify the Type parameter value. Specify the Name parameter value. Save the result to the $mailbox variable.
3. Run the [Get-VBORestorePoint](get-vborestorepoint.md) cmdlet. Set the $repository variable as the Repository parameter value. Provide the Latest parameter. Save the result to the $restorepoint variable.
4. Run the Start-VBODataRetrieval cmdlet. Specify the following settings:

* Set the $restorepoint variable as the RestorePoint parameter value.
* Specify the AvailabilityPeriodDays parameter value.
* Specify the AzureArchiveRetrievalPolicy parameter value.
* Specify the Name parameter value.
* Provide the EnableExpirationNotification parameter.
* Specify the ExpirationHoursThreshold parameter value.
* Set the $mailbox variable as the Mailbox parameter value.

Related Commands

* [Get-VBOEntityData](get-vboentitydata.md)
* [Get-VBORepository](get-vborepository.md)
* [Get-VBORestorePoint](get-vborestorepoint.md)

Page updated 2/25/2025

Page content applies to build 8.3.0.2201
