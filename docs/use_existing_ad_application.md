---
title: "Using Existing Microsoft Entra Application"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/use_existing_ad_application.html"
last_updated: "3/3/2026"
product_version: "8.3.0.2201"
---

# Using Existing Microsoft Entra Application


You can specify an existing Microsoft Entra application in your Microsoft Entra ID. Veeam Backup for Microsoft 365 will use this application for data exchange with your Microsoft 365 organizations during backup and restore sessions.

To use an existing application, do the following:

1. In the Username field, enter a user account that you want to use for impersonation. For more information about impersonation, see [this Microsoft article](https://docs.microsoft.com/en-us/exchange/client-developer/exchange-web-services/impersonation-and-ews-in-exchange).

You can enter any account that belongs to your Microsoft 365 organization using the following format: name@<domain\_name>.<domain>. For example, user@abc.com.

|  |
| --- |
| Note |
| If you plan to back up public folder mailboxes, this user account must be granted the Owner role and have a valid Exchange Online license and an active mailbox within the Microsoft 365 organization. |

Keep in mind that if you select only SharePoint Online and OneDrive for Business services to protect at the [Select Organization Deployment Type](vbo_add_o365_sd.md) step, Veeam Backup for Microsoft 365 displays the Specify organization name field instead. In this field, specify a domain name of your Microsoft 365 organization without the user name. For example, abc.com.

1. In the Application ID field, specify an identification number of Microsoft Entra application that you want to use to access your Microsoft 365 organization.

You can find this number in the application settings of your Microsoft Entra ID. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

1. Click Install to specify a TLS certificate that you want to use for data exchange between Veeam Backup for Microsoft 365 and the specified Microsoft Entra application.

You can generate a new self-signed certificate or use an existing one. When generating a new self-signed certificate, Veeam Backup for Microsoft 365 will register it in Microsoft Entra ID automatically. Before using an existing certificate, make sure to register this certificate in Microsoft Entra ID. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal#certificates-and-secrets).

1. In the Select Certificate wizard, proceed to any of the following options:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Generate a new self-signed certificate

|  |
| --- |
| Perform the following steps:   1. Select the Generate a new self-signed certificate option.   ![Using Existing Microsoft Entra Application](images/select_certificate_wizard_step1_type.webp "Generating New Certificate")   1. Specify a certificate name and click Finish.   ![Using Existing Microsoft Entra Application](images/select_certificate_wizard_step2_create_new.webp "Generating New Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import an existing TLS certificate from the certificate store

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Select certificate from the Certificate Store of this server option.   ![Using Existing Microsoft Entra Application](images/select_certificate_wizard_step1_type_2.webp "Selecting Certificate")   1. Select the certificate from the certificate store and click Finish.   |  | | --- | | Note | | A TLS certificate that you want to use must be added to the Personal certificate store. It also must have a private exportable key. |  ![Using Existing Microsoft Entra Application](images/select_certificate_wizard_step2_pick_from_store.webp "Selecting Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import a TLS certificate from a file in the PFX format

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Import certificate from a PFX file option.   ![Using Existing Microsoft Entra Application](images/select_certificate_wizard_step1_type_3.webp "Importing Certificate")   1. Click Browse and select a PFX file. Specify the certificate password if required.   |  | | --- | | Note | | A TLS certificate that you want to use must have a private exportable key. |  ![Using Existing Microsoft Entra Application](images/select_certificate_wizard_step2_import_file.webp "Importing Certificate")   1. Click Finish. |

1. Select the Grant the required permissions to this application and register its certificate in Microsoft Entra ID check box to automatically grant the [required permissions](ad_app_permissions_sd.md) to Microsoft Entra application.

Veeam Backup for Microsoft 365 will also register the specified certificate in your Microsoft Entra ID.

Keep in mind that you do not need to select this check box if you have granted the required permissions to the specified Microsoft Entra application beforehand and already registered its certificate in Microsoft Entra ID. If the Grant the required permissions to this application and register its certificate in Microsoft Entra ID check box is not selected, Veeam Backup for Microsoft 365 skips the [Log in to Microsoft 365](login_to_microsoft.md) step and proceeds to [Finish Working With Wizard](finish_wizard_sd.md).

![Using Existing Microsoft Entra Application](images/existing_app_sd.webp "Specify Microsoft Entra Application")


