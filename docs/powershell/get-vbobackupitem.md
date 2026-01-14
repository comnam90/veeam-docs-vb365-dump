---
title: "get-vbobackupitem"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbobackupitem.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns a list of objects included in a backup job.

Syntax

|  |
| --- |
| Get-VBOBackupItem [-Organization] -Job <VBOJob> [-Name <String>] [-Users] [-Groups] [-TeamsGroups] [-Sites] [-PersonalSites] [<CommonParameters>] |

Detailed Description

This cmdlet returns an array of objects included in a backup job. The job will back up these objects.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Defines that the cmdlet will return an organization included in a backup job.  Default: False | SwitchParameter | False | Named | False |
| Job | Specifies a backup job. The cmdlet will return objects included in this backup job. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| Name | Specifies a name of an object that is added to a backup job. The cmdlet will return objects with this name.  Note: If you want to get a specific type of an object, you must also set either of the following parameters:   * Organization * Users * Groups * Sites * PersonalSites * TeamsGroups | String | False | Named | False |
| Users | Defines that the cmdlet will return users included in a backup job.  Default: False | SwitchParameter | False | Named | False |
| Groups | Defines that the cmdlet will return groups included in a backup job.  Default: False | SwitchParameter | False | Named | False |
| TeamsGroups | Defines that the cmdlet will return teams included in a backup job.  Default: False | SwitchParameter | False | Named | False |
| Sites | Defines that the cmdlet will return sites included in a backup job.  Default: False | SwitchParameter | False | Named | False |
| PersonalSites | Defines that the cmdlet will return personal sites included in a backup job.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOBackupItem[] object that contains an array of objects included in a backup job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Objects from Backup Job

|  |  |
| --- | --- |
| This example shows how to get all objects that are included in the Monthly Backup job.  |  | | --- | | $job = Get-VBOJob -Name "Monthly Backup"  Get-VBOBackupItem -Job $job |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOBackupItem cmdlet. Set the $job variable as the Job parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Groups from Backup Job

|  |  |
| --- | --- |
| This example shows how to get all groups that are included in the Monthly Backup job.  |  | | --- | | $job = Get-VBOJob -Name "Monthly Backup"  Get-VBOBackupItem -Job $job -Groups |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOBackupItem cmdlet. Set the $job variable as the Job parameter value. Provide the Groups parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Details on Specific Group from Backup Job

|  |  |
| --- | --- |
| This example shows how to get all details of the Team05 group that is included in the Monthly Backup job.  |  | | --- | | $job = Get-VBOJob -Name "Monthly Backup"  $group = Get-VBOBackupItem -Job $job -Groups  $group.Group  OrganizationId : 95141aac-d881-4ba4-b45e-717b0bdfc6ae  OfficeId       : 027f137b-33c0-4be8-a0e0-1263db7f27c2  OnPremisesId   : 00000000-0000-0000-0000-000000000000  DisplayName    : Team05  GroupName      : Team05@Atlanta360.tech  Type           : Office365 |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOBackupItem cmdlet. Set the $job variable as the Job parameter value. Provide the Groups parameter. Save the result to the $group variable. 3. Set the Group property as the $group variable. The object will return the following details on the group: OrganizationId, OfficeId, OnPremisesId, DisplayName, GroupName, Type. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Name of Specific Group from Backup Job

|  |  |
| --- | --- |
| This example shows how to get a name of the Team05 group that is included in the Monthly Backup job.  |  | | --- | | $job = Get-VBOJob -Name "Monthly Backup"  $group = Get-VBOBackupItem -Job $job -Groups  $group.Group.GroupName  GroupName: Team05@Atlanta360.tech |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet. Specify the Name parameter value. Save the result to the $job variable. 2. Run the Get-VBOBackupItem cmdlet. Set the $job variable as the Job parameter value. Provide the Groups parameter. Save the result to the $group variable. 3. Set the Group.GroupName property as the $group variable. The object will return the information on the GroupName property. |

Related Commands

[Get-VBOJob](get-vbojob.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
