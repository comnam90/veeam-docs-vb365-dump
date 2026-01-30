---
title: "Getting Started"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/getting_started.html"
last_updated: "9/16/2025"
product_version: "8.3.0.2201"
---

# Getting Started


Veeam Backup for Microsoft 365 solution comes with four PowerShell modules:

* Veeam.Archiver.PowerShell for Veeam Backup for Microsoft 365
* Veeam.Exchange.PowerShell as part of Veeam Explorer for Microsoft Exchange
* Veeam.Sharepoint.PowerShell as part of Veeam Explorer for Microsoft SharePoint and Veeam Explorer for Microsoft OneDrive for Business
* Veeam.Teams.PowerShell as part of Veeam Explorer for Microsoft Teams

These modules include sets of related PowerShell cmdlets that allow you to perform backup, backup copy, retrieve, configuration and restore operations. Modules are installed by default as part of Veeam Backup for Microsoft 365 and Veeam Explorers.

Consider that actions performed with PowerShell have the same force as actions performed in user interface. For example, if you delete a job with a PowerShell script, the job will be removed from the Veeam Backup for Microsoft 365 database. You will not be able to undo changes.

Requirements

A machine that runs the PowerShell session must have Windows PowerShell version 7.4.2 or later installed.

Starting Veeam Backup for Microsoft 365 PowerShell Sessions

You can run Veeam Backup for Microsoft 365 PowerShell sessions locally or from a remote machine. The remote machine must have the Veeam Backup for Microsoft 365 PowerShell toolkit installed. For more information, see the [Installing PowerShell Toolkit](https://helpcenter.veeam.com/docs/vbo365/guide/vbo_installing_ps.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.

You can open the PowerShell console in Veeam Backup for Microsoft 365 or in Windows PowerShell.

PowerShell Sessions in Veeam Backup for Microsoft 365

You can start a PowerShell session directly from Veeam Backup for Microsoft 365 user interface.

In this case, you will be able to perform actions with Veeam Backup for Microsoft 365 cmdlets without any additional configuration steps. As soon as you run a PowerShell session from Veeam Backup for Microsoft 365, all related PowerShell modules are automatically imported into an active memory.

To start a PowerShell session from Veeam Backup for Microsoft 365 user interface, do the following:

1. In the main menu of Veeam Backup for Microsoft 365, click Console > PowerShell.
2. Connect to a local or remote Veeam Backup for Microsoft 365 server.

For more information on how to connect to a Veeam Backup for Microsoft 365 server, see [Connect-VBOServer](connect-vboserver.md).

PowerShell Sessions in Windows PowerShell

When you install Veeam Backup for Microsoft 365 and Veeam Explorers, all related PowerShell modules are automatically imported into an active memory. If your PowerShell session was opened before you start installation of Veeam Backup for Microsoft 365, run the Import-Module cmdlet to import the Veeam.Archiver.PowerShell module and Veeam Explorers modules. For example:

|  |
| --- |
| Import-Module "C:\Program Files\Veeam\Backup365\Veeam.Archiver.PowerShell\Veeam.Archiver.PowerShell.psd1"  Import-Module "C:\Program Files\Veeam\Backup and Replication\Explorers\Exchange\Veeam.Exchange.PowerShell\Veeam.Exchange.PowerShell.psd1"  Import-Module "C:\Program Files\Veeam\Backup and Replication\Explorers\SharePoint\Veeam.SharePoint.PowerShell\Veeam.SharePoint.PowerShell.psd1"  Import-Module "C:\Program Files\Veeam\Backup and Replication\Explorers\Teams\Veeam.Teams.PowerShell\Veeam.Teams.PowerShell.psd1" |

To start a PowerShell session in Windows PowerShell, do the following:

1. Start a PowerShell session on a machine that has the Veeam Backup for Microsoft 365 PowerShell installed.
2. Connect to a local or remote Veeam Backup for Microsoft 365 server.

For more information on how to connect to a Veeam Backup for Microsoft 365 server, see [Connect-VBOServer](connect-vboserver.md).

In This Section

* [Understanding Veeam Backup for Microsoft 365 Cmdlets](understanding_veeam_cmdlets.md)
* [Using Get-Help](using_get-help.md)
* [Examples of Use](examples_of_use.md)


