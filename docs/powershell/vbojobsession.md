---
title: "VBOJobSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbojobsession.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOJobSession


Contains details about a job session.

| Property | Type | Description |
| --- | --- | --- |
| JobId | GUID | Job ID. |
| JobName | String | Job name. |
| Status | VBOJobStatus | Job status. Possible values:   * Stopped * Running * Success * Failed * Warning * NotConfigured |
| Statistics | [VBOJobStatistics](vbojobstatistics.md) | Job statistics. |
| JobSessionConfigType | VBOJobSessionConfigType | Type of the job synchronization. Possible values:   * Full * Incremental |

Related Commands

[Get-VBOJobSession](get-vbojobsession.md)


