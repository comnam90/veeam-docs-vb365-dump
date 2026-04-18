---
title: "Creating Applications"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/creating_backup_applications.html"
last_updated: "3/13/2026"
product_version: "8.4.0.1457"
---

# Creating Applications


|  |
| --- |
| Note |
| Starting from Veeam Backup for Microsoft 365 version 8.4, creating new applications in your Microsoft Entra ID is not supported. |

When you create a new Microsoft Entra application, Veeam Backup for Microsoft 365 automatically registers this application in Microsoft Entra ID of your Microsoft 365 organization. After you create an application, Veeam Backup for Microsoft 365 automatically adds this application to the backup configuration. For more information about Microsoft Entra applications, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-how-applications-are-added).

To create Microsoft Entra applications and add them to the backup configuration, do the following:

1. Open the Organizations view.
2. In the inventory pane, right-click a Microsoft 365 organization with modern app-only authentication and select Manage backup applications.

Keep in mind that the Manage backup applications option is available only for organizations added using modern app-only authentication. For organizations added using either basic authentication or modern authentication method with legacy protocols allowed, you use the Manage backup accounts option. For more information, see [Adding Accounts](adding_backup_accounts.md).

[![Creating Applications](images/manage_backup_applications.webp)](images/manage_backup_applications.webp "Creating Applications")

1. In the Backup Applications Manager window, click Create.

![Creating Applications](images/manage_backup_applications_create.webp "Backup Applications Manager")

The Create Application wizard runs.

1. Enter a name that you want to use for the Microsoft Entra application.
2. Click Install to specify a TLS certificate for secure communications between Veeam Backup for Microsoft 365 and your backup application.
3. In the Select Certificate wizard, proceed to any of the following options:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Generate a new self-signed certificate

|  |
| --- |
| Perform the following steps:   1. Select the Generate a new self-signed certificate option.   ![Creating Applications](images/select_certificate_wizard_step1_type.webp "Generating New Certificate")   1. Specify a certificate name and click Finish.   ![Creating Applications](images/select_certificate_wizard_step2_create_new.webp "Generating New Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import an existing TLS certificate from the certificate store

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Select certificate from the Certificate Store of this server option.   ![Creating Applications](images/select_certificate_wizard_step1_type_2.webp "Selecting Certificate")   1. Select the certificate from the certificate store and click Finish.   |  | | --- | | Note | | A TLS certificate that you want to use must be added to the Personal certificate store. It also must have a private exportable key. |  ![Creating Applications](images/select_certificate_wizard_step2_pick_from_store.webp "Selecting Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import a TLS certificate from a file in the PFX format

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Import certificate from a PFX file option.   ![Creating Applications](images/select_certificate_wizard_step1_type_3.webp "Importing Certificate")   1. Click Browse and select a PFX file. Specify the certificate password if required.   |  | | --- | | Note | | A TLS certificate that you want to use must have a private exportable key. |  ![Creating Applications](images/select_certificate_wizard_step2_import_file.webp "Importing Certificate")   1. Click Finish. |

Veeam Backup for Microsoft 365 will automatically register the specified certificate in your Microsoft Entra ID and assign this certificate to the Microsoft Entra application. In addition, Veeam Backup for Microsoft 365 automatically grants the Sites.FullControl.All permission to the application.

1. If you want to create more than one Microsoft Entra application, select the Use the same name and certificate to create N applications check box and specify how many applications Veeam Backup for Microsoft 365 must create. Applications may have the same name, however, each application always has a unique identification number. You can create maximum 100 applications per wizard session. If you need to create more than 100 applications, you can click Create and repeat the steps.

![Creating Applications](images/manage_backup_applications_register.webp "Creating Applications")

1. Click Copy code to copy an authentication code.

Keep in mind that a code is valid for 15 minutes. You can click Refresh to request a new code from Microsoft.

1. Click the Microsoft Identity platform authentication server link.

A web browser window opens.

1. On the Sign in to your account webpage, paste the code that you have copied and sign in to Microsoft Identity platform.

Make sure to sign in with the user account that has the Global Administrator role. For more information about this role, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

1. Return to the Create Application wizard and click Finish.

![Creating Applications](images/logon_to_office_365_applications.webp "Creating Applications")


