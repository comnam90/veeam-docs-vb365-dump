---
title: "add-vboexcludedbackupitem"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboexcludedbackupitem.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Creates a list of objects excluded from a backup job.

Syntax

|  |
| --- |
| Add-VBOExcludedBackupItem -Job <VBOJob> -BackupItem <VBOBackupItem[]> [<CommonParameters>] |

Detailed Description

This cmdlet creates a list of objects that will be excluded from a backup job.

Run the [Get-VBOExcludedBackupitem](get-vboexcludedbackupitem.md) cmdlet to get a list of excluded items.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Job | Specifies a backup job. The cmdlet will exclude objects from this backup job. | Accepts the VBOJob object.  To get this object, run the [Get-VBOJob](get-vbojob.md) cmdlet. | True | Named | False |
| BackupItem | Specifies an array of objects that you want to exclude from the backup job.  Note: Team objects can be excluded from the backup job only if the chats option is enabled for this team. | Accepts the VBOBackupItem[] object.  To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Excluding Site Objects

|  |  |
| --- | --- |
| This example shows how to exclude objects of a SharePoint organization site from the Yearly Backup backup job.  |  | | --- | | $yearlyjob = Get-VBOJob -Name "Yearly Backup"  $organization = Get-VBOOrganization -Name "ABC"  $site = "https://exampleorganization.sharepoint.com/sites/excludedsite"  $excludedsite = Get-VBOOrganizationSite -Organization $organization -URL $site  $excludeditems = New-VBOBackupItem -Site $excludedsite  Add-VBOExcludedBackupItem -Job $yearlyjob -BackupItem $excludeditems |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to specify a job to which you want to add a list of excluded items. Set Yearly Backup as the Name parameter value. Save the result to the $yearlyjob variable. 2. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet with the Name parameter to get the organization with the name ABC. Save the result to the $organization variable. 3. Save URL address of a SharePoint organization site that you want to exclude to the $site variable. 4. Run the [Get-VBOOrganizationSite](get-vboorganizationsite.md) cmdlet with the $organization variable and the $site variable as the URL parameter value. Save the result to the $excludedsite variable. 5. Run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet with the $excludedsite variable to create item that represents a SharePoint organization site with a given URL. Save the result to the $excludeditems variable. 6. Run the Add-VBOExcludedBackupItem cmdlet. Set the $yearlyjob variable as the Job parameter value. Set the $excludeditems variable as the BackupItem parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Excluding Objects Specified as Backup Items for Another Backup Job

|  |  |
| --- | --- |
| This example shows how to get backup items from the Yearly Backup backup job and to add them as excluded items to the Monthly Backup backup job.  |  | | --- | | $yearlyjob = Get-VBOJob -Name "Yearly Backup"  $item = Get-VBOBackupItem -Job $yearlyjob  $monthlyjob = Get-VBOJob -Name "Monthly Backup"  Add-VBOExcludedBackupItem -Job $monthlyjob -BackupItem $item |  Perform the following steps:   1. Run the [Get-VBOJob](get-vbojob.md) cmdlet to specify a job from which you want to get items. Set Yearly Backup as the Name parameter value. Save the result to the $yearlyjob variable. 2. Run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. Set the $yearlyjob variable as the Job parameter value. Save the result to the $item variable. 3. Run the [Get-VBOJob](get-vbojob.md) cmdlet to specify a job to which you want to add a list of excluded items. Set Monthly Backup as the Name parameter value. Save the result to the $monthlyjob variable. 4. Run the Add-VBOExcludedBackupItem cmdlet. Set the $monthlyjob variable as the Job parameter value. Set the $item variable as the BackupItem parameter value. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationSite](get-vboorganizationsite.md)
* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
