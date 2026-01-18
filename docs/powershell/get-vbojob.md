---
title: "Get-VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbojob.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOJob


Short Description

Returns backup jobs.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get backup jobs configured in Veeam Backup for Microsoft 365 by the job name or Microsoft organization.

|  |
| --- |
| Get-VBOJob [-Organization <VBOOrganization>] [-Name <String>] [<CommonParameters>] |

* Get a backup job configured in Veeam Backup for Microsoft 365 by the job ID.

|  |
| --- |
| Get-VBOJob -Id <Guid> [<CommonParameters>] |

Detailed Description

This cmdlet returns backup jobs configured in Veeam Backup for Microsoft 365. You can get all backup jobs or query a backup job by name, ID or associated Microsoft organization.

Run the [Get-VBOJobSession](get-vbojobsession.md) cmdlet to get details on the backup job ID and name.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The backup job will back up objects of this organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | False | Named | True (ByValue) |
| Name | Specifies a name of the backup job. The cmdlet will return the backup job with this name. | String | False | Named | False |
| Id | Specifies an ID of the backup job. The cmdlet will return the backup job with this ID. | Guid | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOJob](vbojob.md) object that contains settings for a backup job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Backup Job by ID

|  |  |
| --- | --- |
| This example shows how to get a backup job by ID.  |  | | --- | | Get-VBOJobSession  Get-VBOJob -Id a19840ea-9cf5-413d-af29-57ecad85be9e |  Perform the following steps:   1. Run the [Get-VBOJobSession](get-vbojobsession.md) cmdlet. The cmdlet will return details of all backup jobs. Copy the JobId value from the cmdlet output. 2. Run the Get-VBOJob cmdlet. Set the JobId value as the Id parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Backup Job by Name

|  |  |
| --- | --- |
| This command returns a backup job by name.  |  | | --- | | Get-VBOJob -Name "Monthly Backup" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Backup Job by Name Using Wildcards

|  |  |
| --- | --- |
| This command returns backup jobs with names starting with Sales.  |  | | --- | | Get-VBOJob -Name "Sales\*" | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Backup Job by Microsoft Organization

|  |  |
| --- | --- |
| This example shows how to get backup jobs that are created to back up a specific Microsoft organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOJob -Organization $org |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable. 2. Run the Get-VBOJob cmdlet. Set the $org variable as the Organization parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Getting Backup Job by Name within Microsoft Organization

|  |  |
| --- | --- |
| This example shows how to return a list of backup jobs with names containing Sales within the specified Microsoft organization.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC"  Get-VBOJob -Organization $org -Name "\*Sales\*" |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable. 2. Run the Get-VBOJob cmdlet with the $org variable. Set the $org variable as the Organization parameter value. Specify the Name parameter value. |

Related Commands

* [Get-VBOJobSession](get-vbojobsession.md)
* [Get-VBOOrganization](get-vboorganization.md)


