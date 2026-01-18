---
title: "VBORestoreSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vborestoresession.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# VBORestoreSession


Contains details about a restore session.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Restore session ID. |
| Name | String | Restore session name. |
| StartTime | DateTime | Date and time when the restore session was started. |
| EndTime | DateTime? | Date and time when the restore session ended. |
| PointInTime | DateTime? | Point in time. |
| OrganizationId | GUID? | Microsoft organization ID. |
| OrganizationName | String | Microsoft organization name. |
| Type | VBORestoreSessionType | Restore session type. Possible values:   * Exchange * OneDrive * SharePoint * Teams |
| Status | VBORestoreSessionStatus | Current status of the restore session. Possible values:   * Running * Stopped |
| Result | VBORestoreSessionResult? | Status of the completed restore session. Possible values:   * Success * Warning * Failed |
| InitiatedBy | String | Name of the user that initiated the restore session. |
| Log | [VBORestoreLogItem](vborestorelogitem.md)[] | Array of log items. |
| ProcessedObjects | Int | Number of objects processed by the restore session. |
| ScopeName | String | Scope of the restore session created using Restore Portal. |
| ClientHost | String | DNS name or IP address of the Veeam Backup for Microsoft 365 server. |
| Reason | String | Reason to perform restore operation. |

Related Commands

* [Get-VBORestoreSession](get-vborestoresession.md)
* [Stop-VBORestoreSession](stop-vborestoresession.md)


