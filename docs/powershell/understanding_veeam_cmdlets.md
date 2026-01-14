---
title: "understanding_veeam_cmdlets"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/understanding_veeam_cmdlets.html"
last_updated: "3/25/2025"
product_version: "8.3.0.2201"
---


In this article

A cmdlet is a specialized .NET class that interacts with Microsoft .NET Framework objects. Each cmdlet acts as a single-function command that can perform multiple operations with these objects. Objects represent instances of the Veeam Backup for Microsoft 365 backup infrastructure: backup proxy servers, backup proxy pools, backup repositories, backup and backup copy jobs, restore sessions and so on.

Each cmdlet has parameters that pass additional object data to cmdlet. Parameters can be either required or optional. You will not be able to run a cmdlet without specifying the required parameters, while the optional parameters can be omitted. Parameters are organized into parameter sets that form a syntax of the cmdlet.

Cmdlets and their parameters are named after the Windows PowerShell naming conventions. Veeam cmdlets are developed to behave like other Microsoft Windows cmdlets.

This guide covers only basic information on how to work with Veeam Backup for Microsoft 365 cmdlets using Windows PowerShell. To learn more about Windows PowerShell, see this [Microsoft article](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.5).

Input and Output

As an input, the cmdlets expect objects, and they output objects. The objects represent instances of the Veeam Backup for Microsoft 365 backup infrastructure and can be part of a pipeline.

You can use the cmdlet help to understand what kind of input is needed. The cmdlets have syntax that shows whole sets of parameters available in the cmdlet and what each parameter expects as input. For example, [Add-VBOJob](add-vbojob.md) has the following syntax:

|  |
| --- |
| Add-VBOJob -Organization <VBOOrganization> -Name <String> -Repository <VBORepository> [-EntireOrganization] [-ExcludedItems <VBOBackupItem[]>] [-Description <String>] [-SchedulePolicy <VBOJobSchedulePolicy>] [-RunJob] [-SelectedOneDriveFolders <String[]>] [-ExcludedOneDriveFolders <String[]>] [<CommonParameters>]  Add-VBOJob -Organization <VBOOrganization> -Name <String> -Repository <VBORepository> -SelectedItems <VBOBackupItem[]> [-ExcludedItems <VBOBackupItem[]>] [-Description <String>] [-SchedulePolicy <VBOJobSchedulePolicy>] [-RunJob] [-SelectedOneDriveFolders <String[]>] [-ExcludedOneDriveFolders <String[]>] [<CommonParameters>] |

That means:

* To create a backup job, you need to specify an organization whose items will be processed, the repository where backups will be stored, specify name, description and schedule for this backup job.
* The cmdlet has two parameter sets per different job settings: you can instruct a backup job to process all items or only the selected ones. Use an appropriate parameter set for each case.

Querying Objects

You can use the Name and DisplayName parameters to query objects in the output that the Get cmdlets return. Using query, you can filter results by defined criteria. You can use wildcard characters \* and ? when specifying values for the Name and DisplayName parameters.

Consider the following when using wildcard characters:

* ABC\* — returns all objects with the name or display name started with ABC.
* ?ABC — returns all objects that contain the specified keyword with any symbol in the first position.

For the complete list of supported query parameters, see the [Appendix A. Item Search Parameters](https://helpcenter.veeam.com/docs/vbo365/guide/appendix_search.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.

Page updated 3/25/2025

Page content applies to build 8.3.0.2201
