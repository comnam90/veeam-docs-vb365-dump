---
title: "VBOServerComponent"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboservercomponent.html"
last_updated: "12/8/2025"
product_version: "8.3.0.2201"
---

# VBOServerComponent


Contains details about a component of the Veeam Backup for Microsoft 365 server.

| Property | Type | Description |
| --- | --- | --- |
| Id | GUID | Component ID. |
| Name | String | Component name. |
| ServerName | String | Component server name. |
| IsOnline | Bool | If True, the component is online. |
| ExtendedLoggingEnabled | Bool | If True, the extended logging mode is enabled for this component. |
| DistributedTracingEnabled | Bool | If True, distributed tracing is enabled for this component. |

Related Commands

* [Get-VBOServerComponents](get-vboservercomponents.md)
* [Set-VBOServerComponents](set-vboservercomponents.md)
* [Export-VBOLog](export-vbolog.md)


