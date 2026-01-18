---
title: "VBOOrganizationSynchronizationState"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboorganizationsynchronizationstate.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# VBOOrganizationSynchronizationState


Contains details about synchronization of the organization objects with the organization cache database.

| Property | Type | Description |
| --- | --- | --- |
| Organization | IVBOOrganization | Details about a Microsoft organization. |
| SyncStatus | VBOOrganizationSyncStatus | Synchronization status. Possible values:   * None * Success * Error |
| Type | VBOOrganizationSyncType? | Synchronization type. Possible values:   * Incremental * Full |
| LastSyncTime | DateTime? | Date and time when the synchronization was started for the last time. |
| Error | String | Error occurred during the synchronization operation. |

Related Commands

[Get-VBOOrganizationSynchronizationState](get-vboorganizationsynchronizationstate.md)


