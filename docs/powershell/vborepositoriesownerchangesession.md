---
title: "VBORepositoriesOwnerChangeSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborepositoriesownerchangesession.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# VBORepositoriesOwnerChangeSession


Contains details about a change owner session.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Change owner session ID. |
| Status | RepositoryOwnerChangeStatus | Status of the change owner session. Possible values:   * Waiting * Running * Succeeded * Failed |
| StartTime | DateTime | Date and time when the change owner session was started. |
| EndTime | DateTime? | Date and time when the change owner session ended. |
| Details | String | Change owner session details. |
| Repositories | IReadOnlyCollection | Array of IDs of backup repositories involved in the change owner session. |
| WaitForSessionsTimeout | TimeSpan | Timeout used to wait for the related sessions to finish before starting the current session. |
| ForceStopSessions | Bool | If True, the related sessions are stopped, the change owner session is created and started. |
| ForceStopSessionsTimeout | TimeSpan | Timeout used to wait for the related sessions to stop after Veeam Backup for Microsoft 365 forced them to stop. |
| FromOwnerId | GUID | ID of the backup proxy server or backup proxy poool from which backup repositories are moved. |
| ToOwnerId | GUID | ID of the backup proxy server or backup proxy poool to which backup repositories are moved. |

Related Commands

* [Start-VBORepositoryOwnerChangeSession](start-vborepositoryownerchangesession.md)
* [Get-VBORepositoryOwnerChangeSession](get-vborepositoryownerchangesession.md)


