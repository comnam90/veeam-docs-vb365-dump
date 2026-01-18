---
title: "Add-VBOJob"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vbojob.html"
last_updated: "12/23/2025"
product_version: "8.3.0.2201"
---

# Add-VBOJob


Short Description

Creates a backup job.

Syntax

This cmdlet provides parameter sets that allow you to:

* Create a backup job that will back up all objects of the selected organization except for the specified exclusions.

|  |
| --- |
| Add-VBOJob -Organization <VBOOrganization> -Name <String> -Repository <VBORepository> [-EntireOrganization] [-ExcludedItems <VBOBackupItem[]>] [-Description <String>] [-SchedulePolicy <VBOJobSchedulePolicy>] [-RunJob] [-SelectedOneDriveFolders <String[]>] [-ExcludedOneDriveFolders <String[]>] [<CommonParameters>] |

* Create a backup job that will back up only selected objects to the specified repository.

|  |
| --- |
| Add-VBOJob -Organization <VBOOrganization> -Name <String> -Repository <VBORepository> -SelectedItems <VBOBackupItem[]> [-ExcludedItems <VBOBackupItem[]>] [-Description <String>] [-SchedulePolicy <VBOJobSchedulePolicy>] [-RunJob] [-SelectedOneDriveFolders <String[]>] [-ExcludedOneDriveFolders <String[]>] [<CommonParameters>] |

Detailed Description

This cmdlet creates a backup job that will back up data of your Microsoft 365 and on-premises Microsoft organizations.

|  |
| --- |
| ![Add-VBOJob](images/icon_note.webp) Note |
| Before creating a backup job, make sure you are familiar with the following restrictions:   * Only one backup job can back up an entire organization. * Objects that are already added to the scope of any of your backup jobs will be skipped from the entire organization processing list. * Several jobs cannot back up the same items if you schedule them to run within the same period. If their schedules overlap, the items will be backed up by the job that starts earlier. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The backup job will back up objects of this organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a name of the backup job. The cmdlet will create a backup job with this name. | String | True | Named | False |
| Repository | Specifies a backup repository. Veeam Backup for Microsoft 365 will store backups in this repository.  Note: If you want to create a backup copy job for this backup job, you must specify an object storage repository. | Accepts the [VBORepository](vborepository.md) object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | False |
| EntireOrganization | Defines that the job will back up all objects of the organization.  If you provide this parameter, the cmdlet will add all objects of the organization to the backup job. Otherwise, you must select objects that you want to back up.  Note: The backup job will not back up objects, processed by other backup jobs.  Default: False | SwitchParameter | True | Named | False |
| ExcludedItems | Specifies an array of objects that the job will not back up.  Note: You cannot exclude objects that have been specified for the SelectedItems parameter. | Accepts the [VBOBackupItem](vbobackupitem.md)[] object.   * To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. * To create this object, run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet. | False | Named | False |
| Description | Specifies a description of the backup job.  The default description contains information on the user who added the backup job, date and time when the backup job was added. | String | False | Named | False |
| SchedulePolicy | Specifies schedule settings for a backup job. | Accepts the [VBOJobSchedulePolicy](vbojobschedulepolicy.md) object.  To create this object, run the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) cmdlet. | False | Named | False |
| RunJob | Defines that a backup job will run right after you create it.  If you provide this parameter, the job will start after you run the script. Otherwise, the cmdlet will create a backup job in the stopped status.  Default: False | SwitchParameter | False | Named | False |
| SelectedOneDriveFolders | Specifies an array of OneDrive folders that the job will back up. | String[] | False | Named | False |
| ExcludedOneDriveFolders | Specifies an array of OneDrive folders that a backup job will not back up. | String[] | False | Named | False |
| SelectedItems | Specifies an array of objects that the job will back up. | Accepts the [VBOBackupItem](vbobackupitem.md)[] object.   * To get this object, run the [Get-VBOBackupItem](get-vbobackupitem.md) cmdlet. * To create this object, run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOJob](vbojob.md) object that contains settings for a backup job.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Creating Job to Back Up Selected Items

|  |  |
| --- | --- |
| This example shows how to create a job that will back up selected backup items of an organization except for the exclusions.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC Company"  $repository = Get-VBORepository -Name "ABC Backup Files"  $excludedUser = Get-VBOOrganizationUser -Organization $org -Name "UserAlpha"  $excludedItem = New-VBOBackupItem -Mailbox -User $excludedUser  $item1 = New-VBOBackupItem -Organization $org -Mailbox  Add-VBOJob -Organization $org -Repository $repository -Name "ABC Backup" -SelectedItems $item1 -ExcludedItems $excludedItem -RunJob  Organization       Repository         Name               IsEnabled LastStatus   Description  ------------       ----------         ----               --------- ----------   -----------  ABC Company        ABC Backup Files   ABC Backup         True      Stopped |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 3. Run the [Get-VBOOrganizationUser](get-vboorganizationuser.md) cmdlet. Set the $org variable as the Organization parameter value. Specify the Name parameter value. Save the result to the $excludedUser variable. 4. Run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet. Provide the Mailbox parameter. Set the $excludedUser variable as the User parameter value. Save the result to the $excludedItem variable. 5. Run the [New-VBOBackupItem](new-vbobackupitem.md) cmdlet. Set the $org variable as the Organization parameter value. Provide the Mailbox parameter. Save the result to the $item1 variable. 6. Run the Add-VBOJob cmdlet. Specify the following settings:  * Set the $org variable as the Organization parameter value. * Set the $repository variable as the Repository parameter value. * Specify the Name parameter value. * Set the $item1 variable as the SelectedItems parameter value. * Set the $excludedItem variable as the ExcludedItems parameter value. * Provide the RunJob parameter.   The cmdlet output will contain the following details on the backup job: Organization, Repository, Name, IsEnabled, LastStatus and Description. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Creating Job to Back Up Entire Organization

|  |  |
| --- | --- |
| This example shows how to create a job that will back up the entire organization. Items backed up by other jobs will not be included.  |  | | --- | | $org = Get-VBOOrganization -Name "ABC Company"  $repository = Get-VBORepository -Name "ABC Backup Files"  Add-VBOJob -Name "ABC Backup" -Organization $org -Repository $repository -Description "New Organization" -EntireOrganization -RunJob  Organization       Repository         Name               IsEnabled LastStatus   Description  ------------       ----------         ----               --------- ----------   -----------  ABC Company        ABC Backup Files   ABC Backup           True      Stopped      New Organization |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Specify the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 3. Run the Add-VBOJob cmdlet. Specify the following settings:  * Set the $org variable as the Organization parameter value. * Set the $repository variable as the Repository parameter value.  * Specify the Name parameter value.  * Provide the EntireOrganization parameter. * Provide the RunJob parameter.   The cmdlet output will contain the following details on the backup job: Organization, Repository, Name, IsEnabled, LastStatus and Description. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBORepository](get-vborepository.md)
* [Get-VBOOrganizationUser](get-vboorganizationuser.md)
* [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md)
* [New-VBOBackupItem](new-vbobackupitem.md)
* [Get-VBOBackupItem](get-vbobackupitem.md)


