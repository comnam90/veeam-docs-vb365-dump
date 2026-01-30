---
title: "Permissions for Service Account on Windows"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_windows.html"
last_updated: "9/6/2024"
product_version: "8.3.0.2201"
---

# Permissions for Service Account on Windows


This section contains permissions required by Veeam Backup for Microsoft 365 for a service account that is used to run Veeam Backup for Microsoft 365 Proxy Service on a Windows-based backup proxy server. By default, Veeam Backup for Microsoft 365 uses Local System account, but you can use a service account of your own.

The following are required permissions for a service account on a Windows-based backup proxy server:

* The account must have Log on as a service right.
* Full Access to the C:\Windows\Temp folder.
* Full Access for the HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\SystemCertificates\My registry key.
* For the HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Services\VSS\VssAccessControl registry key, a new value must be created with the account name as a value name and set to 1.
* The account must be a member of the Performance Monitor Users security group.

Related Topics

[Adding Windows-Based Backup Proxy Server](add_win_proxy.md)


