---
title: "get-vboorganizationsynchronizationstate"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationsynchronizationstate.html"
last_updated: "4/10/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Returns status of synchronization of Microsoft organization objects with the organization cache database.

|  |
| --- |
| ![Get-VBOOrganizationSynchronizationState](images/icon_note.webp) Note |
| Synchronization of objects with the organization cache database is only available for Microsoft organizations with modern app-only authentication. |

Syntax

|  |
| --- |
| Get-VBOOrganizationSynchronizationState -Organization <IVBOOrganization> [<CommonParameters>] |

Detailed Description

This cmdlet returns status of synchronization of Microsoft organization objects with the organization cache database.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return synchronization status for objects of this Microsoft organization. | IVBOOrganization  Accepts the VBOOrganization object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOOrganizationSynchronizationState object that contains details on the synchronization status of the organization objects with the organization cache database.

Example

Getting Synchronization Status

This example shows how to get status of synchronization of Microsoft organization objects with the organization cache database.

|  |
| --- |
| $org = Get-VBOOrganization  Get-VBOOrganizationSynchronizationState -Organization $org  Organization : abc.onmicrosoft.com  SyncStatus   : Success  Type         : Incremental  LastSyncTime : 10/5/2023 4:54:11 PM  Error        : |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Save the result to the $org variable.
2. Run the Get-VBOOrganizationSynchronizationState cmdlet. Set the $org variable as the Organization parameter value.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)

Page updated 4/10/2025

Page content applies to build 8.3.0.2201
