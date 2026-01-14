---
title: "get-vboexcludedbackupitem"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboexcludedbackupitem.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns a list of objects excluded from a backup job.

Syntax

|  |
| --- |
| Get-VBOExcludedBackupItem -Job <VBOJob> [-Name <String>] [-Users] [-Groups] [-TeamsGroups] [-Sites] [-PersonalSites] [<CommonParameters>] |

Detailed Description

This cmdlet returns a list of objects excluded from a backup job.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job. The cmdlet will return objects excluded from this job. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| Name | Specifies a name of an object. The cmdlet will return objects with this name.  Note: If you want to get a specific type of an object, you must also set either of the following parameters:   * Users * Groups * Sites * PersonalSites * TeamsGroups | String | False | Named | False |
| Users | Defines that the cmdlet will return users excluded from a backup job.  Default: False | SwitchParameter | False | Named | False |
| Groups | Defines that the cmdlet will return groups excluded from a backup job.  Default: False | SwitchParameter | False | Named | False |
| TeamsGroups | Defines that the cmdlet will return teams excluded from a backup job.  Default: False | SwitchParameter | False | Named | False |
| Sites | Defines that the cmdlet will return sites excluded from a backup job.  Default: False | SwitchParameter | False | Named | False |
| PersonalSites | Defines that the cmdlet will return personal sites excluded from a backup job.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting Excluded Objects

|  |  |
| --- | --- |
| This example shows how to get a list of objects excluded from the Monthly Backup job.  |  | | --- | | $job = Get-VBOJob -Name "Monthly Backup"  Get-VBOExcludedBackupItem -Job $job |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Set Monthly Backup as the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOExcludedBackupItem cmdlet. Set the $job variable as the Job parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Excluded Groups

|  |  |
| --- | --- |
| This example shows how to get a list of groups excluded from the Yearly Backup job.  |  | | --- | | $job = Get-VBOJob -Name "Yearly Backup"  Get-VBOExcludedBackupItem -Job $job -Groups |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Set Yearly Backup as the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOExcludedBackupItem cmdlet. Set the $job variable as the Job parameter value. Provide the Groups parameter. |

Related Commands

[Get-VBOJob](get-vbojob.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
