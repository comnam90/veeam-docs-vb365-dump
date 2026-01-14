---
title: "removing_backup_applications"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/removing_backup_applications.html"
last_updated: "2/14/2025"
product_version: "8.3.0.2201"
---


In this article

You can update an SSL certificate of each configured Microsoft Entra application or you can remove an application from the backup configuration if you no longer want to use it. For more information on how to configure backup applications, see [Adding Applications](adding_backup_applications.md) and [Creating Applications](creating_backup_applications.md).

Updating Certificate

To update a certificate, do the following:

1. Open the Organizations view.
2. In the inventory pane, right-click an organization and select Manage backup applications.
3. In the Backup Applications Manager window, in the Certificate column, click Configured next to the Microsoft Entra application whose certificate you want to update.
4. Update the certificate using the Select Certificate wizard. To do this, proceed to any of the following options:

* [Select certificate from the Certificate Store of this server](vbo_installing_certificate.md#selecting_file)
* [Import certificate from a PFX file](vbo_installing_certificate.md#import)

Removing Application

To remove an application, do the following:

1. Open the Organizations view.
2. In the inventory pane, right-click an organization and select Manage backup applications.
3. In the Backup Applications Manager window, select Microsoft Entra application that you want to remove in the list and click Remove.

You can select multiple applications using the [CTRL] key.

Page updated 2/14/2025

Page content applies to build 8.3.0.2201
