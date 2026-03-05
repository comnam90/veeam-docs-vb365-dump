---
title: "Updating Certificates and Removing Applications"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/removing_backup_applications.html"
last_updated: "2/18/2026"
product_version: "8.3.0.2201"
---

# Updating Certificates and Removing Applications


You can update a TLS certificate of each configured Microsoft Entra application or you can remove an application from the backup configuration if you no longer want to use it. For more information on how to configure backup applications, see [Adding Applications](adding_backup_applications.md) and [Creating Applications](creating_backup_applications.md).

Updating Certificate

To update a certificate, do the following:

1. Open the Organizations view.
2. In the inventory pane, right-click an organization and select Manage backup applications.
3. In the Backup Applications Manager window, in the Certificate column, click Configured next to the Microsoft Entra application whose certificate you want to update.
4. Update the certificate using the Select Certificate wizard. To do this, proceed to any of the following options:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import an existing TLS certificate from the certificate store

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Select certificate from the Certificate Store of this server option.   ![Updating Certificates and Removing Applications](images/select_certificate_wizard_step1_type_2.webp "Selecting Certificate")   1. Select the certificate from the certificate store and click Finish.   |  | | --- | | Note | | A TLS certificate that you want to use must be added to the Personal certificate store. It also must have a private exportable key. |  ![Updating Certificates and Removing Applications](images/select_certificate_wizard_step2_pick_from_store.webp "Selecting Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import a TLS certificate from a file in the PFX format

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Import certificate from a PFX file option.   ![Updating Certificates and Removing Applications](images/select_certificate_wizard_step1_type_3.webp "Importing Certificate")   1. Click Browse and select a PFX file. Specify the certificate password if required.   |  | | --- | | Note | | A TLS certificate that you want to use must have a private exportable key. |  ![Updating Certificates and Removing Applications](images/select_certificate_wizard_step2_import_file.webp "Importing Certificate")   1. Click Finish. |

Removing Application

To remove an application, do the following:

1. Open the Organizations view.
2. In the inventory pane, right-click an organization and select Manage backup applications.
3. In the Backup Applications Manager window, select Microsoft Entra application that you want to remove in the list and click Remove.

You can select multiple applications using the [CTRL] key.


