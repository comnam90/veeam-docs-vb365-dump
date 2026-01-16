---
title: "permissions_changelog"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_changelog.html"
last_updated: "9/6/2024"
product_version: "8.3.0.2201"
---


In this article

This section contains information about changes in permissions required for Veeam Backup for Microsoft 365 version 8.3 comparing to version 7.0.

Microsoft Entra Application Permissions

The following table lists changes in permissions for modern app-only authentication:

| API | Permission name | Type | Usage | Description | Status |
| --- | --- | --- | --- | --- | --- |
| Microsoft Graph | ChannelMember.Read.All | Application | Backup | Accessing Microsoft Teams private and shared channels. | new |
| ChannelMember.ReadWrite.All | Delegated | Restore | Reading the current state and restoring Microsoft Teams private and shared channels using device code flow. | new |
| ChannelMember.ReadWrite.All | Application | Restore | Reading the current state and restoring Microsoft Teams private and shared channels using the Microsoft Entra application certificate. | new |
| Files.ReadWrite.All | Application | Restore | Reading the current state and restoring files of Microsoft Teams shared channels. | new |

Linux-based Backup Proxy Server

You can add Linux-based backup proxy servers to the Veeam Backup for Microsoft 365 backup infrastructure. A service account must be granted permissions to run Veeam Backup for Microsoft 365 Proxy Service on a machine with Linux operating systems installed. For more information, see [Permissions for Service Account on Linux](permissions_linux.md).

Windows-based Backup Proxy Server

You can add Windows-based backup proxy servers to the Veeam Backup for Microsoft 365 backup infrastructure. A service account must be granted permissions to run Veeam Backup for Microsoft 365 Proxy Service on a machine with Windows operating systems installed. For more information, see [Permissions for Service Account on Windows](permissions_windows.md).

Page updated 9/6/2024

Page content applies to build 8.3.0.2201
