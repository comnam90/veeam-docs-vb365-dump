---
title: "examples_of_use"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/examples_of_use.html"
last_updated: "5/29/2024"
product_version: "8.3.0.2201"
---


In this article

This section describes how to use a PowerShell script to create a backup job.

To create a backup job, use the [Add-VBOJob](add-vbojob.md) cmdlet. The cmdlet has two parameter sets: for processing all items of an organization or only the selected ones. For creating a backup job that processes all items of an organization, you must specify values for the following required parameters:

* -Organization. Specify the organization that is added to the Veeam Backup for Microsoft 365 infrastructure. The backup job will process the items of this organization. For more information on how to add an organization to the Veeam Backup for Microsoft 365 infrastructure, see the [Add-VBOOrganization](add-vboorganization.md) cmdlet.
* -Repository. Specify the backup repository that is added to the Veeam Backup for Microsoft 365 infrastructure. Backups will be stored in this repository. For more information on how to add a repository to the Veeam Backup for Microsoft 365 infrastructure, see the [Add-VBORepository](add-vborepository.md) cmdlet.
* -Name. Specify the name of the backup job that you want to create.
* -EntireOrganization. If indicated, the backup job will process all items of the organization.

To create a backup job, do the following:

1. Get the VBOOrganization object using the [Get-VBOOrganization](get-vboorganization.md) cmdlet and save the result to the $org variable:

|  |
| --- |
| $org = Get-VBOOrganization -Name "ABC Company" |

1. Get the VBORepository object using the [Get-VBORepository](get-vborepository.md) cmdlet and save the result to the $repository variable:

|  |
| --- |
| $repository = Get-VBORepository -Name "ABC Email Backup" |

1. Create a backup job with the ABC Backup Job name. Use the saved $org and $repository variables as the Organization and Repository parameters value:

|  |
| --- |
| Add-VBOJob –Organization $org –Repository $repository –Name "ABC Backup Job" -EntireOrganization |

Page updated 5/29/2024

Page content applies to build 8.3.0.2201
