---
title: "Get-VBORestorePoint"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vborestorepoint.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# Get-VBORestorePoint


Short Description

Returns restore points.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get restore points for a specific Veeam Backup for Microsoft 365 organization or backup repository.

|  |
| --- |
| Get-VBORestorePoint [-Organization <VBOOrganization>] [-Repository <VBORepository>] [-IsLongTermCopy] [-IsCopy] [-IsRetrieved] [-Latest] [<CommonParameters>] |

* Get restore points created by a specific backup job.

|  |
| --- |
| Get-VBORestorePoint -Job <VBOJob> [-Repository <VBORepository>] [-Latest] [<CommonParameters>] |

Detailed Description

This cmdlet returns restore points stored in Veeam Backup for Microsoft 365. Once you get restore points, you can do the following:

* Start restore sessions to explore and restore backed-up Microsoft Exchange objects, SharePoint items, OneDrive items, and Microsoft Teams objects using the following cmdlets:

* [Start-VBOExchangeItemRestoreSession](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/start-vboexchangeitemrestoresession.html?ver=80)
* [Start-VBOSharePointItemRestoreSession](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/start-vbosharepointitemrestoresession.html?ver=80)
* [Start-VEODRestoreSession](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/start-veodrestoresession.html?ver=80)
* [Start-VBOTeamsItemRestoreSession](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/start-vboteamsitemrestoresession.html?ver=80)

* Create and start a retrieval job to retrieve data from backup copies created by Veeam Backup for Microsoft 365 in an object storage repository. For more information, see [Start-VBODataRetrieval](start-vbodataretrieval.md).

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return restore points created for this organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | True (ByValue) |
| Repository | Specifies a backup repository. The cmdlet will return restore points created for this backup repository. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | False | Named | False |
| IsLongTermCopy | Defines that the cmdlet will return restore points created by backup copy jobs in the following object storage repositories:   * Azure Blob Storage Archive access tier * all Amazon S3 Glacier storage classes   Default: False | SwitchParameter | False | Named | False |
| IsCopy | Defines that the cmdlet will return restore points created by backup copy jobs in all object storage repositories.  Default: False | SwitchParameter | False | Named | False |
| IsRetrieved | Defines that the cmdlet will return restore points created by a retrieval job.  Default: False | SwitchParameter | False | Named | False |
| Latest | Defines that the cmdlet will return only the latest restore point.  Default: False | SwitchParameter | False | Named | False |
| Job | Specifies a backup job. The cmdlet will return restore points created by this backup job. | Accepts the [VBOJob](vbojob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns an array of [VBORestorePoint](vborestorepoint.md) objects created by Veeam Backup for Microsoft 365.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Restore Points

|  |  |
| --- | --- |
| This command returns restore points created by all backup jobs in Veeam Backup for Microsoft 365.  |  | | --- | | Get-VBORestorePoint | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Restore Points for Specific Backup Job

|  |  |
| --- | --- |
| This example shows how to get restore points created by Veeam Backup for Microsoft 365 for a specific backup job.  |  | | --- | | $job = Get-VBOJob -Name "Backup: Sales Mailbox"  Get-VBORestorePoint -Job $job |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet with the Name parameter to get the backup job for which you want to get restore points. Save the result to the $job variable. 2. Run the Get-VBORestorePoint cmdlet. Set the $job variable as the Job parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Restore Points for Specific Organization

|  |  |
| --- | --- |
| This example shows how to get restore points created by Veeam Backup for Microsoft 365 for a specific organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBORestorePoint -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $org variable. 2. Run the Get-VBORestorePoint cmdlet. Set the $org variable as the Organization parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Starting Exchange Items Restore Session

|  |  |
| --- | --- |
| This example shows how to start a restore session to explore backed-up Microsoft Exchange objects for the first restore point of a specific backup job.  |  | | --- | | $job = Get-VBOJob -Name "Backup: Sales Mailbox"  $restorepoint = (Get-VBORestorePoint -Job $job | Sort -Property BackupTime)  Start-VBOExchangeItemRestoreSession -RestorePoint $restorepoint[0] |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet with the Name parameter to get the backup job for which you want to start a restore session. Save the result to the $job variable. 2. Run the Get-VBORestorePoint cmdlet to get an array of restore points automatically sorted descending by BackupTime. Set the $job variable as the Job parameter value. Save the result to the $restorepoint variable. 3. Run the [Start-VBOExchangeItemRestoreSession](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/start-vboexchangeitemrestoresession.html?ver=80) cmdlet. Set the $restorepoint variable as the RestorePoint parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Getting Restore Points for Azure Blob Storage Archive

|  |  |
| --- | --- |
| This example shows how to get restore points created by Veeam Backup for Microsoft 365 for Azure Blob Storage Archive.  |  | | --- | | $archiverepo = Get-VBORepository -Name "Azure Blob Storage Archive" -LongTerm  Get-VBORestorePoint -Repository $archiverepo -IsLongTermCopy |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet with the Name parameter. Provide the LongTerm parameter. Save the result to the $archiverepo variable. 2. Run the Get-VBORestorePoint cmdlet. Set the $archiverepo variable as the Repository parameter value. Provide the IsLongTermCopy parameter. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBORepository](get-vborepository.md)
* [Start-VBOExchangeItemRestoreSession](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/start-vboexchangeitemrestoresession.html?ver=80)


